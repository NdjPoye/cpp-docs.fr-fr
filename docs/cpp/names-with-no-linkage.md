---
title: Noms avec aucune liaison | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- functions [C++], parameters
- typedef names, linkage
- enumerators [C++], linkage
- names [C++], with no linkage
- function parameters [C++]
ms.assetid: 7174c500-12d2-4572-8c16-63c27c758fb1
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 161698d01e9cc9aeaac8f2b9bdc491343555880d
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="names-with-no-linkage"></a>Noms avec aucune liaison
Les seuls noms n'ayant aucune liaison sont :  
  
-   Paramètres de fonction.  
  
-   Noms de portée de bloc non déclaré comme `extern` ou **statique**.  
  
-   Énumérateurs.  
  
-   Noms déclarés dans une instruction `typedef`. Exception : lorsque l'instruction `typedef` est utilisée pour fournir un nom pour un type de classe non nommé. Le nom peut ensuite posséder une liaison externe si la classe en possède une. L'exemple suivant illustre une situation dans laquelle un nom `typedef` possède une liaison externe :  
  
    ```  
    // names_with_no_linkage.cpp  
    typedef struct  
    {  
       short x;  
       short y;  
    } POINT;  
  
    extern int MoveTo( POINT pt );  
  
    int main()  
    {  
    }  
    ```  
  
     Le nom `typedef`, `POINT`, devient le nom de classe de la structure sans nom. Il est ensuite utilisé pour déclarer une fonction avec liaison externe.  
  
 Étant donné que les noms `typedef` ne possèdent aucune liaison, leurs définitions peuvent différer entre les différentes unités de traduction. Étant donné que les compilations sont discrètes, le compilateur ne peut pas détecter ces différences. En conséquence, les erreurs de ce type sont uniquement détectées au moment de la liaison. Prenons le cas suivant :  
  
```  
// Translation unit 1  
typedef int INT  
  
INT myInt;  
...  
  
// Translation unit 2  
typedef short INT  
  
extern INT myInt;  
...  
```  
  
 Le code précédent génère une erreur « externe non résolue » au moment de la liaison.  
  
## <a name="example"></a>Exemple  
 Les fonctions C++ peuvent être définies uniquement dans la portée du fichier ou de la classe. L'exemple suivant montre comment définir des fonctions et présente une définition de fonction erronée :  
  
```  
// function_definitions.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
void ShowChar( char ch );    // Declare function ShowChar.  
  
void ShowChar( char ch )     // Define function ShowChar.  
{                            // Function has file scope.  
   cout << ch;  
}  
  
struct Char                  // Define class Char.  
{  
    char Show();             // Declare Show function.  
    char Get();              // Declare Get function.  
    char ch;  
};  
  
char Char::Show()            // Define Show function  
{                            //  with class scope.  
    cout << ch;  
    return ch;  
}  
  
void GoodFuncDef( char ch )  // Define GoodFuncDef  
{                            //  with file scope.  
    int BadFuncDef( int i )  // C2601, Erroneous attempt to  
    {                        //  nest functions.  
        return i * 7;  
    }  
    for( int i = 0; i < BadFuncDef( 2 ); ++i )  
        cout << ch;  
    cout << "\n";  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Programme et liaison](../cpp/program-and-linkage-cpp.md)
