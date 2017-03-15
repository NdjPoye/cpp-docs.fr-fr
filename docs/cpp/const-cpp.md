---
title: "const (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "const_cpp"
  - "const"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const (mot clé) (C++)"
ms.assetid: b21c0271-1ad0-40a0-b21c-5e812bba0318
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# const (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lors de la modification d'une déclaration de données, le mot clé **const** spécifie que l'objet ou la variable n'est pas modifiable.  
  
## Syntaxe  
  
```  
  
        const declaration ;  
member-function const ;  
```  
  
## Valeurs const  
 Le mot clé **const** indique que la valeur d'une variable est constante et fait en sorte que compilateur empêche le programmeur de la modifier.  
  
```  
// constant_values1.cpp  
int main() {  
   const int i = 5;  
   i = 10;   // C3892  
   i++;   // C2105  
}  
```  
  
 En C\+\+, vous pouvez utiliser le mot clé **const** au lieu de la directive de préprocesseur [\#define](../preprocessor/hash-define-directive-c-cpp.md) pour définir des valeurs constantes.  Les valeurs définies avec **const** sont soumises à la vérification du type et peuvent être utilisées à la place des expressions constantes.  En C\+\+, vous pouvez spécifier la taille d'un tableau avec une variable **const** comme suit :  
  
```  
// constant_values2.cpp  
// compile with: /c  
const int maxarray = 255;  
char store_char[maxarray];  // allowed in C++; not allowed in C  
```  
  
 En C, les valeurs de constante utilisent par défaut la liaison externe. Elles ne peuvent donc apparaître que dans des fichiers sources.  En C\+\+, les valeurs de constante utilisent par défaut la liaison interne, ce qui leur permet d'apparaître dans les fichiers d'en\-tête.  
  
 Le mot clé **const** peut également être utilisé dans les déclarations de pointeur.  
  
```  
// constant_values3.cpp  
int main() {  
   char *mybuf = 0, *yourbuf;  
   char *const aptr = mybuf;  
   *aptr = 'a';   // OK  
   aptr = yourbuf;   // C3892  
}  
```  
  
 Un pointeur vers une variable déclarée comme **const** peut être assigné uniquement à un pointeur qui est également déclaré comme **const**.  
  
```  
// constant_values4.cpp  
#include <stdio.h>  
int main() {  
   const char *mybuf = "test";  
   char *yourbuf = "test2";  
   printf_s("%s\n", mybuf);  
  
   const char *bptr = mybuf;   // Pointer to constant data  
   printf_s("%s\n", bptr);  
  
   // *bptr = 'a';   // Error  
}  
```  
  
 Vous pouvez utiliser des pointeurs vers des données constantes comme paramètres de fonction pour empêcher la fonction de modifier un paramètre passé par l'intermédiaire d'un pointeur.  
  
 Pour les objets déclarés comme **const**, vous ne pouvez appeler que des [fonctions membres de constantes](../misc/constant-member-functions.md).  Cela garantit que l'objet constant n'est jamais modifié.  
  
```  
birthday.getMonth();    // Okay  
birthday.setMonth( 4 ); // Error  
```  
  
 Vous pouvez appeler des fonctions membres de constante ou non constante pour un objet non constant.  Vous pouvez aussi surcharger une fonction membre avec le mot clé **const** ; cela permet d'appeler une version différente de la fonction pour les objets constants et non constants.  
  
 Vous ne pouvez pas déclarer de constructeurs ou de destructeurs avec le mot clé **const**.  
  
## Fonctions membres const  
 La déclaration d'une fonction membre avec le mot clé **const** indique que la fonction est une fonction « Lecture seule » qui ne modifie pas l'objet pour lequel elle est appelée.  Une fonction membre constante ne peut pas modifier les données membres non statiques ni appeler des fonctions membres qui ne sont pas constantes. Pour déclarer une fonction membre constante, placez le mot clé **const** après la parenthèse fermante de la liste d'arguments.  Le mot clé **const** est requis dans la déclaration et la définition.  
  
```  
// constant_member_function.cpp  
class Date  
{  
public:  
   Date( int mn, int dy, int yr );  
   int getMonth() const;     // A read-only function  
   void setMonth( int mn );   // A write function; can't be const  
private:  
   int month;  
};  
  
int Date::getMonth() const  
{  
   return month;        // Doesn't modify anything  
}  
void Date::setMonth( int mn )  
{  
   month = mn;          // Modifies data member  
}  
int main()  
{  
   Date MyDate( 7, 4, 1998 );  
   const Date BirthDate( 1, 18, 1953 );  
   MyDate.setMonth( 4 );    // Okay  
   BirthDate.getMonth();    // Okay  
   BirthDate.setMonth( 4 ); // C2662 Error  
}  
```  
  
## Différences entre const en C et C\+\+  
 Lorsque vous déclarez une variable comme **const** dans un fichier de code source C, vous procédez comme suit :  
  
```  
const int i = 2;  
```  
  
 Vous pouvez ensuite utiliser cette variable dans un autre module comme suit :  
  
```  
extern const int i;  
```  
  
 En revanche, pour obtenir le même comportement en C\+\+, vous devez déclarer votre variable **const** comme suit :  
  
```  
extern const int i = 2;  
```  
  
 Si vous souhaitez déclarer une variable `extern` dans un fichier de code source C\+\+ pour l'utiliser dans un fichier de code source C, utilisez :  
  
```  
extern "C" const int x=10;  
```  
  
 pour empêcher que le compilateur C\+\+ altère les noms.  
  
## Notes  
 En suivant la liste des paramètres d'une fonction membre, le mot clé **const** indique que la fonction ne modifie pas l'objet pour lequel elle est appelée.  
  
 Pour plus d'informations sur **const**, consultez les rubriques suivantes :  
  
-   [Valeurs constantes](../misc/constant-values.md)  
  
-   [Fonctions membres de constante](../misc/constant-member-functions.md)  
  
-   [Pointeurs const et volatile](../cpp/const-and-volatile-pointers.md)  
  
-   [Qualificateurs de type \(référence du langage C\)](../c-language/type-qualifiers.md)  
  
-   [volatile](../cpp/volatile-cpp.md)  
  
-   [\#define](../preprocessor/hash-define-directive-c-cpp.md).  
  
## Voir aussi  
 [Mots clés C\+\+](../cpp/keywords-cpp.md)