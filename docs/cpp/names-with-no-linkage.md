---
title: "Noms avec aucune liaison | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "énumérateurs (C++), liaison"
  - "paramètres de fonction (C++)"
  - "fonctions (C++), paramètres"
  - "noms (C++), sans liaison"
  - "noms typedef, liaison"
ms.assetid: 7174c500-12d2-4572-8c16-63c27c758fb1
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Noms avec aucune liaison
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les seuls noms n'ayant aucune liaison sont :  
  
-   Paramètres de fonction.  
  
-   Noms ayant une portée de bloc non déclarés comme `extern` ou **static**.  
  
-   Énumérateurs.  
  
-   Noms déclarés dans une instruction `typedef`.  Exception : lorsque l'instruction `typedef` est utilisée pour fournir un nom pour un type de classe non nommé.  Le nom peut ensuite posséder une liaison externe si la classe en possède une.  L'exemple suivant illustre une situation dans laquelle un nom `typedef` possède une liaison externe :  
  
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
  
     Le nom `typedef`, `POINT`, devient le nom de classe de la structure sans nom.  Il est ensuite utilisé pour déclarer une fonction avec liaison externe.  
  
 Étant donné que les noms `typedef` ne possèdent aucune liaison, leurs définitions peuvent différer entre les différentes unités de traduction.  Étant donné que les compilations sont discrètes, le compilateur ne peut pas détecter ces différences.  En conséquence, les erreurs de ce type sont uniquement détectées au moment de la liaison.  Prenons le cas suivant :  
  
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
  
## Exemple  
 Les fonctions C\+\+ peuvent être définies uniquement dans la portée du fichier ou de la classe.  L'exemple suivant montre comment définir des fonctions et présente une définition de fonction erronée :  
  
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
  
## Voir aussi  
 [Programme et liaison](../cpp/program-and-linkage-cpp.md)