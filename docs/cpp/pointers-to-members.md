---
title: Pointeurs vers des membres | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- declarations, pointers
- class members [C++], pointers to
- pointers, to members
- members [C++], pointers to
- pointers, declarations
ms.assetid: f42ddb79-9721-4e39-95b1-c56b55591f68
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0354d0a910db0f4237a56607a7322acb7a1b57a0
ms.sourcegitcommit: 3c1930dc1e7e69fdbb431029cd3e9b9b00a140cc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/31/2018
ms.locfileid: "34686849"
---
# <a name="pointers-to-members"></a>Pointeurs vers membres
Les déclarations de pointeurs vers des membres sont des cas spéciaux de déclarations de pointeur.  Elles sont déclarées à l'aide de la séquence suivante :  
  
```  
[storage-class-specifiers] [cv-qualifiers] type-specifiers [ms-modifier]qualified-name ::* [cv-qualifiers] identifier  
[= & qualified-name :: member-name];  
```  
  
1.  Spécificateur de déclaration :  
  
    -   Spécificateur de classe de stockage facultatif.  
  
    -   Facultatif **const** et/ou `volatile` spécificateurs.  
  
    -   Spécificateur de type : nom d'un type.  Il s'agit du type du membre vers lequel pointer, et non de la classe.  
  
2.  Déclarateur :  
  
    -   Modificateur spécifique Microsoft facultatif. Pour plus d’informations, consultez [modificateurs spécifiques Microsoft](../cpp/microsoft-specific-modifiers.md).  
  
    -   Nom qualifié de la classe contenant les membres vers lesquels pointer.   
  
    -   Opérateur ::.  
  
    -   Le **\*** opérateur.  
  
    -   Facultatif **const** et/ou `volatile` spécificateurs.  
  
    -   Identificateur nommant le pointeur vers le membre.  
  
    -   Initialiseur facultatif :  
  
 Le **=** opérateur.  
  
 Le **&** opérateur.  
  
 Nom qualifié de la classe.  
  
 opérateur `::`,  
  
 Nom d'un membre non statique de la classe du type approprié.  
  
 Comme toujours, les déclarateurs multiples (et tout initialiseur associé) sont autorisés dans une même déclaration.  
  
 Un pointeur vers un membre d'une classe diffère d'un pointeur normal, car il comporte des informations de type pour le type du membre et pour la classe à laquelle le membre appartient. Un pointeur normal identifie (a l'adresse de) un seul objet en mémoire. Un pointeur vers un membre d'une classe identifie ce membre dans toute instance de la classe. L'exemple suivant déclare une classe, `Window`, et certains pointeurs vers des données membres.  
  
```  
// pointers_to_members1.cpp  
class Window  
{  
public:  
   Window();                               // Default constructor.  
   Window( int x1, int y1,                 // Constructor specifying  
   int x2, int y2 );                       //  window size.  
bool SetCaption( const char *szTitle ); // Set window caption.  
   const char *GetCaption();               // Get window caption.  
   char *szWinCaption;                     // Window caption.  
};  
  
// Declare a pointer to the data member szWinCaption.  
char * Window::* pwCaption = &Window::szWinCaption;  
int main()  
{  
}  
```  
  
 Dans l’exemple précédent, `pwCaption` est un pointeur vers un membre de classe `Window` qui possède un type **char\***. Le type de `pwCaption` est `char * Window::* `. Le fragment de code suivant déclare des pointeurs vers les fonctions membres `SetCaption` et `GetCaption`.  
  
```  
const char * (Window::*pfnwGC)() = &Window::GetCaption;  
bool (Window::*pfnwSC)( const char * ) = &Window::SetCaption;  
```  
  
 Les pointeurs `pfnwGC` et `pfnwSC` pointent respectivement vers `GetCaption` et `SetCaption` de la classe `Window`. Le code copie directement des informations vers le titre de la fenêtre à l'aide du pointeur vers le membre `pwCaption` :  
  
```  
Window wMainWindow;  
Window *pwChildWindow = new Window;  
char   *szUntitled    = "Untitled -  ";  
int    cUntitledLen   = strlen( szUntitled );  
  
strcpy_s( wMainWindow.*pwCaption, cUntitledLen, szUntitled );  
(wMainWindow.*pwCaption)[cUntitledLen - 1] = '1';     //same as  
//wMainWindow.SzWinCaption [cUntitledLen - 1] = '1';  
strcpy_s( pwChildWindow->*pwCaption, cUntitledLen, szUntitled );   
(pwChildWindow->*pwCaption)[cUntitledLen - 1] = '2'; //same as //pwChildWindow->szWinCaption[cUntitledLen - 1] = '2';  
```  
  
 La différence entre la **.\***  et **-> \*** opérateurs (les opérateurs de pointeur vers membre) est que le **.\***  opérateur sélectionne des membres étant donné un objet ou une référence d’objet, alors que le **-> \*** opérateur sélectionne des membres via un pointeur. (Pour plus d’informations sur ces opérateurs, consultez [Expressions avec opérateurs pointeur vers membre](../cpp/pointer-to-member-operators-dot-star-and-star.md).)  
  
 Le résultat des opérateurs pointeur vers membre est le type du membre : dans ce cas, **char \*** .  
  
 Le fragment de code suivant appelle les fonctions membres `GetCaption` et `SetCaption` à l'aide de pointeurs vers des membres :  
  
```  
// Allocate a buffer.  
enum {  
    sizeOfBuffer = 100  
};  
char szCaptionBase[sizeOfBuffer];  
  
// Copy the main window caption into the buffer  
//  and append " [View 1]".  
strcpy_s( szCaptionBase, sizeOfBuffer, (wMainWindow.*pfnwGC)() );  
strcat_s( szCaptionBase, sizeOfBuffer, " [View 1]" );  
// Set the child window's caption.  
(pwChildWindow->*pfnwSC)( szCaptionBase );  
```  
  
## <a name="restrictions-on-pointers-to-members"></a>Restrictions sur les pointeurs vers des membres  
 L'adresse d'un membre statique n'est pas un pointeur vers un membre. C'est un pointeur normal vers l'instance du membre statique. Étant donné que qu’une seule instance d’un membre statique existe pour tous les objets d’une classe donnée, le normales d’adresse **(&)** et déréférencer **(\*)** opérateurs peuvent être utilisés.  
  
## <a name="pointers-to-members-and-virtual-functions"></a>Pointeurs vers des membres et des fonctions virtuelles  
 L'appel d'une fonction virtuelle via une fonction pointeur vers membre fonctionne comme si la fonction avait été appelée directement. La fonction correcte est recherchée dans la v-table et appelée.  
  
 La clé du bon fonctionnement des fonctions virtuelles est, comme toujours, de les appeler via un pointeur vers une classe de base. (Pour plus d’informations sur les fonctions virtuelles, consultez [fonctions virtuelles](../cpp/virtual-functions.md).)  
  
 Le code suivant montre comment appeler une fonction virtuelle via un pointeur de fonction membre :  
  
```  
// virtual_functions.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
class Base  
{  
public:  
virtual void Print();  
};  
void (Base ::* bfnPrint)() = &Base :: Print;  
void Base :: Print()  
{  
cout << "Print function for class Base\n";  
}  
  
class Derived : public Base  
{  
public:  
void Print();  // Print is still a virtual function.  
};  
  
void Derived :: Print()  
{  
cout << "Print function for class Derived\n";  
}  
  
int main()  
{  
    Base   *bPtr;  
    Base    bObject;  
Derived dObject;  
bPtr = &bObject;    // Set pointer to address of bObject.  
(bPtr->*bfnPrint)();  
bPtr = &dObject;    // Set pointer to address of dObject.  
(bPtr->*bfnPrint)();  
}  
  
//Output: Print function for class Base  
Print function for class Derived  
```  
  
## <a name="see-also"></a>Voir aussi  
 
