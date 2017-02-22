---
title: "Pointeur this | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "this"
  - "this_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fonctions membres non statiques"
  - "pointeurs, vers des instances de classe"
  - "ce pointeur"
ms.assetid: 92e3256a-4ad9-4d46-8be1-d77fad90791f
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Pointeur this
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le pointeur **this** est accessible uniquement dans les fonctions membres non statiques de type **classe**, `struct` ou **union**.  Il pointe vers l'objet pour lequel la fonction membre est appelée.  Les fonctions membres statiques n'ont pas de pointeur **this**.  
  
## Syntaxe  
  
```  
  
        this   
this->member-identifier  
```  
  
## Notes  
 Le pointeur **this** d'un objet ne fait pas partie de l'objet lui\-même ; il n'est pas répercuté dans le résultat d'une instruction `sizeof` sur l'objet.  En revanche, lorsqu'une fonction membre non statique est appelée pour un objet, l'adresse de l'objet est passée par le compilateur comme argument masqué à la fonction.  Par exemple, l'appel de fonction suivant :  
  
```  
myDate.setMonth( 3 );  
```  
  
 peut être interprété de cette façon :  
  
```  
setMonth( &myDate, 3 );  
```  
  
 L'adresse de l'objet est disponible à partir de la fonction membre en tant que pointeur **this**.  La plupart des utilisations de **this** sont implicites.  Il est permis, bien qu'inutile, d'utiliser explicitement **this** lorsqu'il est fait référence aux membres de la classe.  Exemple :  
  
```  
void Date::setMonth( int mn )  
{  
   month = mn;            // These three statements  
   this->month = mn;      // are equivalent  
   (*this).month = mn;  
}  
```  
  
 L'expression `*this` est utilisée couramment pour retourner l'objet actuel d'une fonction membre :  
  
```  
return *this;  
```  
  
 Le pointeur **this** est également utilisé pour la protection contre les autoréférences :  
  
```  
if (&Object != this) {  
// do not execute in cases of self-reference  
```  
  
> [!NOTE]
>  Le pointeur **this** étant non modifiable, les assignations à **this** ne sont pas autorisées.  Les implémentations précédentes de C\+\+ autorisaient les assignations à **this**.  
  
 Parfois, le pointeur **this** est utilisé directement \(par exemple, pour manipuler les structures de données auto\-référentielles, où l'adresse de l'objet actif est requise\).  
  
## Exemple  
  
```  
// this_pointer.cpp  
// compile with: /EHsc  
  
#include <iostream>  
#include <string.h>  
  
using namespace std;  
  
class Buf   
{  
public:  
    Buf( char* szBuffer, size_t sizeOfBuffer );  
    Buf& operator=( const Buf & );  
    void Display() { cout << buffer << endl; }  
  
private:  
    char*   buffer;  
    size_t  sizeOfBuffer;  
};  
  
Buf::Buf( char* szBuffer, size_t sizeOfBuffer )  
{  
    sizeOfBuffer++; // account for a NULL terminator  
  
    buffer = new char[ sizeOfBuffer ];  
    if (buffer)  
    {  
        strcpy_s( buffer, sizeOfBuffer, szBuffer );  
        sizeOfBuffer = sizeOfBuffer;  
    }  
}  
  
Buf& Buf::operator=( const Buf &otherbuf )   
{  
    if( &otherbuf != this )   
    {  
        if (buffer)  
            delete [] buffer;  
  
        sizeOfBuffer =  strlen( otherbuf.buffer ) + 1;   
        buffer = new char[sizeOfBuffer];  
        strcpy_s( buffer, sizeOfBuffer, otherbuf.buffer );  
    }  
    return *this;  
}  
  
int main()  
{  
    Buf myBuf( "my buffer", 10 );  
    Buf yourBuf( "your buffer", 12 );  
  
    // Display 'my buffer'  
    myBuf.Display();  
  
    // assignment opperator  
    myBuf = yourBuf;  
  
    // Display 'your buffer'  
    myBuf.Display();  
}  
```  
  
  **ma mémoire tampon**  
**votre mémoire tampon**   
## Type du pointeur this  
 Le type du pointeur **this** peut être modifié dans la déclaration d'une fonction par les mots clés **const** et `volatile`.  Pour déclarer une fonction comme ayant les attributs d'un ou plusieurs de ces mots clés, ajoutez le ou les mots clés après la liste d'arguments de la fonction.  
  
 Considérez cet exemple :  
  
```  
// type_of_this_pointer1.cpp  
class Point  
{  
    unsigned X() const;  
};  
int main()  
{  
}  
```  
  
 Le code précédent déclare une fonction membre, `X`, dans laquelle le pointeur **this** est traité comme un pointeur **const** désignant un objet **const**.  Des combinaisons des options *cv\-mod\-list* peuvent être utilisées, mais elles modifient toujours l'objet désigné par **this** et non pas le pointeur **this** lui\-même.  Par conséquent, la déclaration ci\-dessous déclare la fonction `X` ; le pointeur **this** est un pointeur **const** désignant un objet **const** :  
  
```  
// type_of_this_pointer2.cpp  
class Point  
{  
    unsigned X() const;  
};  
int main()  
{  
}  
```  
  
 Le type du pointeur **this** dans une fonction membre est décrit par la syntaxe suivante, où *cv\-qualifier\-list* est déterminé à partir du déclarateur de fonction membre et peut être **const** ou **volatile** \(ou les deux\), et où *class\-type* est le nom de la classe :  
  
 *\[cv\-qualifier\-list\] class\-type*  **\* const this**  
  
 En d'autres termes, **this** est toujours un pointeur const ; il ne peut pas être réassigné.  Les qualificateurs **const** ou `volatile` utilisés dans la déclaration de fonction membre s'appliquent à l'instance de classe désignée par **this** dans la portée de cette fonction.  
  
 Le tableau ci\-dessous fournit davantage d'explications sur le fonctionnement de ces modificateurs.  
  
### Sémantique des modificateurs du pointeur this  
  
|Modificateur|Signification|  
|------------------|-------------------|  
|**const**|Impossible de modifier les données membres ; impossible d'appeler les fonctions membres qui ne sont pas **const**.|  
|`volatile`|Les données membres sont chargées à partir de la mémoire chaque fois que vous y accédez ; certaines optimisations sont désactivées.|  
  
 Il est incorrect de passer un objet **const** à une fonction membre qui n'est pas **const**.  De même, il est incorrect de passer un objet `volatile` à une fonction membre qui n'est pas `volatile`.  
  
 Les fonctions membres déclarées comme **const** ne peuvent pas modifier les données membres \(dans ces fonctions, le pointeur **this** désigne un objet **const**\).  
  
> [!NOTE]
>  Il est impossible de déclarer des constructeurs ou des destructeurs comme **const** ou `volatile`.  Ils peuvent, toutefois, être appelés sur des objets **const** ou `volatile`.  
  
## Voir aussi  
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [Type de pointeur this](../misc/type-of-this-pointer.md)   
 [Argument correspondant et pointeur this](../misc/argument-matching-and-the-this-pointer.md)