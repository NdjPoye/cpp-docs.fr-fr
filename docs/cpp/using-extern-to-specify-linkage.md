---
title: "Utilisation d’extern pour spécifier la liaison | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- extern
dev_langs:
- C++
helpviewer_keywords:
- extern keyword [C++], linkage to non-C++ functions
- declarations, external
- external linkage, extern modifier
ms.assetid: 1e2f0ae3-ae98-4410-85b5-222d6abc865a
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: b17479bfda8dbe009d3b2381afc2d87819811bc5
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="using-extern-to-specify-linkage"></a>Utilisation d'extern pour spécifier la liaison
## <a name="syntax"></a>Syntaxe  
  
```  
  
      extern string-literal { declaration-list }  
extern string-literal declaration  
```  
  
## <a name="remarks"></a>Remarques  
 Le mot clé `extern` déclare une variable ou une fonction, et spécifie qu'elle possède une liaison externe (son nom est visible à partir de fichiers autres que celui dans lequel elle est définie). Lorsque vous modifiez une variable, `extern` spécifie que la variable a une durée statique (elle est allouée lorsque le programme démarre et libérée lorsque le programme se termine). La variable ou la fonction peut être définie dans un autre fichier source ou plus tard dans le même fichier. Les déclarations de variables et de fonctions au niveau de la portée du fichier sont externes par défaut.  
  
## <a name="example"></a>Exemple  
  
```  
// specifying_linkage1.cpp  
int i = 1;  
void other();  
  
int main() {  
   // Reference to i, defined above:  
   extern int i;  
}  
  
void other() {  
   // Address of global i assigned to pointer variable:  
   static int *external_i = &i;  
  
   // i will be redefined; global i no longer visible:  
   // int i = 16;  
}  
```  
  
 En langage C++, lorsqu'il est utilisé avec une chaîne, le mot clé `extern` spécifie que les conventions de liaison d'un autre langage sont utilisées pour le ou les déclarateurs. Les données et les fonctions C sont accessibles uniquement si elles sont déclarées auparavant comme ayant une liaison C. Toutefois, elles doivent être définies dans une unité de traduction compilée séparément.  
  
 Microsoft C++ prend en charge les chaînes **« C »** et **« C++ »** dans les *littéral de chaîne* champ. Tous les fichiers Include standard utilisent la syntaxe `extern` "C" pour permettre aux fonctions de la bibliothèque Runtime d'être utilisées dans les programmes C++.  
  
## <a name="example"></a>Exemple  
 L'exemple ci-dessous illustre d'autres méthodes qui permettent de déclarer des noms possédant une liaison C :  
  
```  
// specifying_linkage2.cpp  
// compile with: /c  
// Declare printf with C linkage.  
extern "C" int printf( const char *fmt, ... );  
  
//  Cause everything in the specified header files  
//   to have C linkage.  
extern "C" {  
   // add your #include statements here  
   #include <stdio.h>  
}  
  
//  Declare the two functions ShowChar and GetChar  
//   with C linkage.  
extern "C" {  
   char ShowChar( char ch );  
   char GetChar( void );  
}  
  
//  Define the two functions ShowChar and GetChar  
//   with C linkage.  
extern "C" char ShowChar( char ch ) {  
   putchar( ch );  
   return ch;  
}  
  
extern "C" char GetChar( void ) {  
   char ch;  
  
   ch = getchar();  
   return ch;  
}  
  
// Declare a global variable, errno, with C linkage.  
extern "C" int errno;  
```  
  
 Si une fonction a plusieurs spécifications de liaison, ils doivent concorder ; le fait de déclarer des fonctions comme ayant à la fois une liaison C et une liaison C++ constitue une erreur. En outre, si deux déclarations pour une fonction se produisent dans un programme (une avec une spécification de liaison et une autre sans), la déclaration avec la spécification de la liaison doit être la première. Toutes les déclarations redondantes de fonctions qui ont déjà une spécification de liaison sont affectées de la liaison spécifiée dans la première déclaration. Exemple :  
  
```  
extern "C" int CFunc1();  
...  
int CFunc1();            // Redeclaration is benign; C linkage is  
                         //  retained.  
  
int CFunc2();  
...  
extern "C" int CFunc2(); // Error: not the first declaration of  
                         //  CFunc2;  cannot contain linkage  
                         //  specifier.  
```  
  
 Fonctions et objets déclarés explicitement comme **statique** dans le corps d’un spécificateur de liaison composé (**{}**) sont traités en tant que fonctions statiques ou des objets ; le spécificateur de liaison est ignoré. Les autres fonctions et objets se comportent comme s'ils étaient déclarés avec le mot clé `extern`. (Consultez [utilisation d’extern pour spécifier la liaison](../cpp/using-extern-to-specify-linkage.md) pour plus d’informations sur la `extern` (mot clé).)  
  
## <a name="see-also"></a>Voir aussi  
 [Mots clés](../cpp/keywords-cpp.md)   
 [Spécificateur extern de classe de stockage](../c-language/extern-storage-class-specifier.md)   
 [Comportement des identificateurs](../c-language/behavior-of-identifiers.md)   
 [Liaison](../c-language/linkage.md)
