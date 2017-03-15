---
title: "Comment&#160;: &#233;tablir une interface entre le code exceptionnel et le code non exceptionnel | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: fd5bb4af-5665-46a1-a321-614b48d4061e
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Comment&#160;: &#233;tablir une interface entre le code exceptionnel et le code non exceptionnel
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique comment implémenter une gestion cohérente des exceptions dans un module C\+\+, et également comment traduire ces exceptions depuis et vers des codes d'erreur aux limites de l'exception.  
  
 Parfois un module C\+\+ doit s'interfacer avec du code qui n'utilise pas d'exceptions \(code non exceptionnel\).  Cette interface est appelée *une limite d'exception*.  Par exemple, vous pouvez appeler la fonction `CreateFile` Win32 dans votre programme C\+\+.  `CreateFile` ne lève pas d'exception ; en revanche il définit des codes d'erreur qui peuvent être extraits par la fonction `GetLastError`.  Si votre programme C\+\+ est non trivial, vous préférez probablement qu'il ait une stratégie cohérente de gestion d'erreurs basée sur les exceptions.  Et vous ne souhaitez probablement pas abandonner d'exceptions uniquement parce que vous vous travaillez avec du code non\-exceptionnel, ni mélanger des stratégies de gestion d'erreurs basées sur des exception et d'autres qui ne le sont pas dans votre module C\+\+.  
  
## Appel de fonctions non exceptionnelles depuis C\+\+  
 Lorsque vous appelez une fonction non exceptionnelle en C\+\+, l'idée consiste à encapsuler cette fonction dans une fonction C\+\+ qui détecte toutes les erreurs puis lève éventuellement une exception.  Lorsque vous concevez une telle fonction d'encapsulation, décidez d'abord le type de garantie de levée d'exception à fournir : pas de levée d'exception, garantie forte, ou garantie de base.  Ensuite, créez la fonction de manière à ce que toutes les ressources, par exemple, les file handles, soient correctement libérés si une exception est levée.  En général, cela signifie que vous utilisez des pointeurs intelligents ou des gestionnaires de ressources semblables qui possèdent les ressources.  Pour plus d'informations sur les questions liées au design, consultez [Comment : conception pour la sécurité des exceptions](../cpp/how-to-design-for-exception-safety.md).  
  
### Exemple  
 L'exemple suivant illustre les fonctions C\+\+ qui utilisent les fonctions Win32 `CreateFile` et `ReadFile` en interne pour ouvrir et lire deux fichiers.  La classe `File` est un wrapper de RAII \(Resource Acquisition is Initialization pour les file handles.  Son constructeur détecte un état « fichier introuvable » et lève une exception pour propager l'erreur en haut de la pile des appels du module C\+\+ \(dans cet exemple, la fonction `main()` \).  Si une exception est levée après qu'un objet `File` soit entièrement construit, le destructeur appelle automatiquement `CloseHandle` pour libérer le file handle. \(Si vous préférez, utilisez la classe `CHandle` Active Template Library \(ATL\) pour ce même objectif, ou `unique_ptr` avec un destructeur personnalisé.\) Les fonctions qui appellent Win32 et les API CRT détectent des erreurs puis lèvent des exceptions C\+\+ à l'aide de la fonction définie localement `ThrowLastErrorIf`, qui utilise ensuite la classe `Win32Exception`, dérivée de la classe `runtime_error`.  Toutes les fonctions dans cet exemple fournissent une garantie forte d'exception ; si une exception est levée à tout moment dans ces fonctions, aucune ressource ne fuit et aucun état de votre programme n'est modifié.  
  
```cpp  
// compile with: /EHsc  
#include <Windows.h>  
#include <stdlib.h>  
#include <vector>  
#include <iostream>  
#include <string>  
#include <limits>  
#include <stdexcept>  
  
using namespace std;  
  
string FormatErrorMessage(DWORD error, const string& msg)  
{  
    static const int BUFFERLENGTH = 1024;  
    vector<char> buf(BUFFERLENGTH);  
    FormatMessageA(FORMAT_MESSAGE_FROM_SYSTEM, 0, error, 0, buf.data(),   
        BUFFERLENGTH - 1, 0);   
    return string(buf.data()) + "   ("  + msg  + ")";  
}  
  
class Win32Exception : public runtime_error  
{      
private:  
    DWORD m_error;  
public:  
    Win32Exception(DWORD error, const string& msg)  
        : runtime_error(FormatErrorMessage(error, msg)), m_error(error) { }  
  
    DWORD GetErrorCode() const { return m_error; }  
};  
  
void ThrowLastErrorIf(bool expression, const string& msg)   
{   
    if (expression) {   
        throw Win32Exception(GetLastError(), msg);   
    }   
}   
  
class File  
{  
private:  
    HANDLE m_handle;  
  
    // Declared but not defined, to avoid double closing.  
    File& operator=(const File&);  
    File(const File&);  
public:  
    explicit File(const string& filename)   
    {  
        m_handle = CreateFileA(filename.c_str(), GENERIC_READ, FILE_SHARE_READ,   
            nullptr, OPEN_EXISTING, FILE_ATTRIBUTE_READONLY, nullptr);  
        ThrowLastErrorIf(m_handle == INVALID_HANDLE_VALUE,   
            "CreateFile call failed on file named " + filename);  
    }  
  
    ~File() { CloseHandle(m_handle); }  
  
    HANDLE GetHandle() { return m_handle; }  
};  
  
size_t GetFileSizeSafe(const string& filename)  
{  
    File fobj(filename);  
    LARGE_INTEGER filesize;  
  
    BOOL result = GetFileSizeEx(fobj.GetHandle(), &filesize);  
    ThrowLastErrorIf(result == FALSE, "GetFileSizeEx failed: " + filename);  
  
    if (filesize.QuadPart < (numeric_limits<size_t>::max)()) {  
        return filesize.QuadPart;  
    } else {  
        throw;   
    }  
}  
  
vector<char> ReadFileVector(const string& filename)  
{  
    File fobj(filename);  
    size_t filesize = GetFileSizeSafe(filename);  
    DWORD bytesRead = 0;  
  
    vector<char> readbuffer(filesize);  
  
    BOOL result = ReadFile(fobj.GetHandle(), readbuffer.data(), readbuffer.size(),   
        &bytesRead, nullptr);  
    ThrowLastErrorIf(result == FALSE, "ReadFile failed: " + filename);  
  
    cout << filename << " file size: " << filesize << ", bytesRead: "   
        << bytesRead << endl;  
  
    return readbuffer;  
}  
  
bool IsFileDiff(const string& filename1, const string& filename2)   
{  
    return ReadFileVector(filename1) != ReadFileVector(filename2);  
}   
  
#include <iomanip>  
  
int main ( int argc, char* argv[] )  
{  
    string filename1("file1.txt");  
    string filename2("file2.txt");  
  
    try  
    {  
        if(argc > 2) {  
            filename1 = argv[1];  
            filename2 = argv[2];  
        }   
  
        cout << "Using file names " << filename1 << " and " << filename2 << endl;  
  
        if (IsFileDiff(filename1, filename2)) {  
            cout << "*** Files are different." << endl;  
        } else {  
            cout<< "*** Files match." << endl;  
        }  
    }  
    catch(const Win32Exception& e)  
    {          
        ios state(nullptr);  
        state.copyfmt(cout);  
        cout << e.what() << endl;  
        cout << "Error code: 0x" << hex << uppercase << setw(8) << setfill('0')   
            << e.GetErrorCode() << endl;  
        cout.copyfmt(state); // restore previous formatting  
    }  
}  
  
```  
  
## Appel de code exceptionnel appel depuis un code non exceptionnel  
 Les fonctions C\+\+ déclarées comme « externes C » peuvent être appelées par des programmes C.  Les serveurs COM C\+\+ peuvent être utilisés par du code écrit dans un certain nombre de langages.  Lorsque vous implémentez des fonctions publiques conscientes des exception en C\+\+ destinées à être appelées par du code non exceptionnelle, la fonction C\+\+ ne doit autoriser les exceptions à se propager vers l'appelant.  Par conséquent, la fonction C\+\+ doit spécifiquement intercepter chaque exception qu'elle sait gérer et, le cas échéant, convertir l'exception en un code d'erreur que l'appelant comprends.  Si toutes les exceptions potentielles ne sont pas connues, la fonction C\+\+ doit avoir un bloc `catch(…)` comme le dernier gestionnaire.  Dans de tels cas, il est préférable de signaler une erreur irrécupérable à l'appelant, car votre programme peut être dans un état inconnu.  
  
 L'exemple suivant illustre une fonction qui suppose que toute exception qui peut être levée est soit une exception Win32 ou un type d'exception dérivé de `std::exception`.  La fonction intercepte toute exception de ces types et propage les informations d'erreur sous la forme d'un code d'erreur Win32 à l'appelant.  
  
```cpp  
BOOL DiffFiles2(const string& file1, const string& file2)   
{   
    try   
    {   
        File f1(file1);   
        File f2(file2);   
        if (IsTextFileDiff(f1, f2))   
        {   
            SetLastError(MY_APPLICATION_ERROR_FILE_MISMATCH);   
            return FALSE;   
        }   
        return TRUE;   
    }   
    catch(Win32Exception& e)   
    {   
        SetLastError(e.GetErrorCode());   
    }  
  
    catch(std::exception& e)   
    {   
        SetLastError(MY_APPLICATION_GENERAL_ERROR);   
    }   
    return FALSE;   
}  
  
```  
  
 Lorsque vous convertissez des exceptions en codes d'erreur, un problème potentiel est que les codes d'erreur ne contiennent souvent pas la richesse d'information qu'une exception peut stocker.  Pour résoudre ce problème, vous pouvez fournir un bloc `catch` pour chaque type d'exception spécifique qui peut être levée, puis exécuter l'enregistrement pour stocker les détails de l'exception avant qu'elle ne soit convertie en code d'erreur.  Cette approche peut créer beaucoup de redondance de code si plusieurs fonctions utilisent toutes le même ensemble de blocs `catch`.  Un bon moyen d'éviter la répétition de code est de refactoriser ces blocs dans une fonction de service privée qui implémente les blocs `try` et `catch` et qui accepte un objet de fonction qui est appelé dans un bloc `try`.  Dans chaque fonction publique, passez\-le à la fonction de service comme expression lambda.  
  
```cpp  
template<typename Func>   
bool Win32ExceptionBoundary(Func&& f)   
{   
    try   
    {   
        return f();   
    }   
    catch(Win32Exception& e)   
    {   
        SetLastError(e.GetErrorCode());   
    }   
    catch(const std::exception& e)   
    {   
        SetLastError(MY_APPLICATION_GENERAL_ERROR);   
    }   
    return false;   
}  
  
```  
  
 L'exemple suivant montre comment écrire l'expression lambda qui définit la fonction.  Lorsqu'une fonction est définie « inline » en utilisant une expression lambda, elle est souvent plus facile à lire qu'elle ne le serait serait si elle était écrite comme un objet nommé de fonction.  
  
```cpp  
bool DiffFiles3(const string& file1, const string& file2)   
{   
    return Win32ExceptionBoundary([&]() -> bool  
    {   
        File f1(file1);   
        File f2(file2);   
        if (IsTextFileDiff(f1, f2))   
        {   
            SetLastError(MY_APPLICATION_ERROR_FILE_MISMATCH);   
            return false;   
        }   
        return true;   
    });   
}  
  
```  
  
 Pour plus d'informations sur les expressions lambda, consultez [Expressions lambda](../cpp/lambda-expressions-in-cpp.md).  
  
## Voir aussi  
 [Gestion des erreurs et des exceptions](../cpp/errors-and-exception-handling-modern-cpp.md)   
 [Comment : conception pour la sécurité des exceptions](../cpp/how-to-design-for-exception-safety.md)