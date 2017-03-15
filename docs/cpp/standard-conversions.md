---
title: "Conversions standard | Microsoft Docs"
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
  - "conversions, standard"
  - "valeurs L"
  - "conversions standard, catégories de"
ms.assetid: ce7ac8d3-5c99-4674-8229-0672de05528d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Conversions standard
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le langage C\+\+ définit les conversions entre ses types fondamentaux.  Il définit également les conversions pour les types dérivés de pointeur, de référence et de pointeur vers membre.  Ces conversions sont appelées « conversions standard ». \(Pour plus d'informations sur les types, types standard et types dérivés, consultez  [Types](http://msdn.microsoft.com/fr-fr/6882ee83-ea32-4373-8d57-c3efbbc15af0).\)  
  
 Cette section décrit les conversions standard suivantes :  
  
-   [Promotions intégrales](../misc/integral-promotions.md)  
  
-   [Conversions intégrales](../misc/integral-conversions.md)  
  
-   [Conversions flottantes](../misc/floating-conversions.md)  
  
-   [Conversions flottantes et intégrales](../misc/floating-and-integral-conversions.md)  
  
-   [Conversions arithmétiques](../misc/arithmetic-conversions.md)  
  
-   [Conversions de pointeurs](../misc/pointer-conversions-cpp.md)  
  
-   [Conversions de références](../misc/reference-conversions.md)  
  
-   [Conversions de pointeur vers membre](../misc/pointer-to-member-conversions.md)  
  
    > [!NOTE]
    >  Les types définis par l'utilisateur peuvent spécifier leurs propres conversions.  La conversion des types définis par l'utilisateur est décrite dans [Constructeurs](../cpp/constructors-cpp.md) et [Conversions](../cpp/user-defined-type-conversions-cpp.md).  
  
 Le code suivant provoque des conversions \(dans cet exemple, promotions intégrales\) :  
  
```  
long  lnum1, lnum2;  
int   inum;  
  
// inum promoted to type long prior to assignment.  
lnum1 = inum;  
  
// inum promoted to type long prior to multiplication.  
lnum2 = inum * lnum2;  
```  
  
> [!NOTE]
>  Le résultat d'une conversion est une l\-value uniquement si elle produit un type référence.  Par exemple, une conversion définie par l'utilisateur déclarée sous la forme  
  
```  
operator int&()  
```  
  
> [!NOTE]
>  retourne une référence et est une l\-value.  En revanche, une conversion déclarée sous la forme  
  
```  
operator int()  
```  
  
> [!NOTE]
>  retourne un objet et n'est pas une l\-value.  
  
## Promotions intégrales  
 Les objets d'un type intégral peuvent être convertis en un autre type intégral plus large \(autrement dit, un type qui peut représenter un plus grand ensemble de valeurs\).  Ce type étendu de conversion est appelé « promotion d'un intégral ». La promotion d'un intégral vous permet d'utiliser ce qui suit dans une expression partout où un autre type d'intégral peut être utilisé :  
  
-   Objets, littéraux et constantes de type `char` et `short int`  
  
-   Types d'énumération  
  
-   Champ de bits `int`  
  
-   Énumérateurs  
  
 Les promotions C\+\+ sont de type « conservation\-valeur ». Autrement dit, vous pouvez être sûr que la valeur suivent la promotion est identique à celle qui la précède.  Dans les promotions de type conservation\-valeur, des objets des types intégraux plus courts \(tels que les champs de bits ou des objets de type `char`\) sont promus au type `int` si `int` peut représenter la plage complète du type d'origine.  Si `int` ne peut pas représenter la plage de valeurs complète, l'objet est transformé en type `unsigned int`.  Bien que cette stratégie soit la même que celle utilisée par C ANSI, les conversions de type conservation\-valeur ne conservent pas « l'entier non signé » de l'objet.  
  
 Les promotions de type conservation\-valeur et les promotions qui conservent l'entier non signé produisent normalement les mêmes résultats.  Toutefois, ils peuvent produire des résultats différents si l'objet promu est l'un des suivants :  
  
-   Un opérande **\/**, `%`, `/=`, `%=`, **\<**, **\<\=**, **\>** ou **\>\=**  
  
     Ces opérateurs se basent sur un signe pour déterminer le résultat.  Par conséquent, les promotions de type conservation\-valeur et conservation\-signe produisent des résultats différents lorsqu'elles sont appliquées à ces opérandes.  
  
-   L'opérande gauche **\>\>** ou **\>\>\=**  
  
     Ces opérateurs traitent les quantités signées et non signées différemment en effectuant une opération de décalage.  Pour les quantités signées, le déplacement de la quantité vers la droite provoque la propagation du bit de signe dans les positions binaires libérées.  Pour les quantités non signées, les positions binaires libérées sont vides.  
  
-   Argument vers une fonction ou un opérande surchargé d'un opérateur surchargé qui dépend de l'entier non signé du type de l'opérande pour la correspondance d'argument.  \(Consultez [Opérateurs surchargés](../cpp/operator-overloading.md) pour en savoir plus sur la définition des opérateurs surchargés.\)  
  
## Conversions intégrales  
 Des conversions intégrales sont effectuées entre les types intégraux.  Les types intégraux sont `char`, `int` et **long** \(ainsi que les versions **short**, **signed** et `unsigned` de ces types\).  
  
 **Type signé en type non signé**  
  
 Les objets de types intégraux signés peuvent être convertis en types non signés correspondants.  Lorsque ces conversions ont lieu, le modèle binaire réel ne change pas. Toutefois, l'interprétation des données change.  Prenons le code suivant :  
  
```  
// conve__pluslang_Converting_Signed_to_Unsigned.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
int main()  
{  
    short  i = -3;  
    unsigned short u;  
  
    cout << (u = i) << "\n";  
}  
// Output: 65533  
  
```  
  
 Dans l'exemple précédent, `signed short`, `i`, est défini et initialisé à un nombre négatif.  L'expression `(u = i)` entraîne la conversion de `i` en **unsigned short** avant l'assignation à `u`.  
  
 **Type non signé en type signé**  
  
 Les objets de types intégraux non signés peuvent être convertis en types signés correspondants.  Toutefois, cette conversion peut entraîner une erreur d'interprétation des données si la valeur de l'objet non signé se situe en dehors de la plage qui peut être représentée par le type signé, comme illustré dans l'exemple suivant :  
  
```  
// conve__pluslang_Converting_Unsigned_to_Signed.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
int main()  
{  
 short  i;  
 unsigned short u = 65533;  
  
 cout << (i = u) << "\n";  
}  
//Output: -3  
```  
  
 Dans l'exemple précédent, `u` est un objet intégral `unsigned`**short** qui doit être converti en une quantité signée pour évaluer l'expression `(i = u)`.  Étant donné que sa valeur ne peut pas être correctement représentée dans un `signed short`, les données sont mal interprétées, comme il est indiqué.  
  
## Conversions de nombres à virgule flottante  
 Un objet de type flottant peut être converti sans risque en type flottant plus précis. Cela permet de ne pas perdre de signification lors de la conversion.  Par exemple, les conversions de **float** à **double** ou de **double** à `long double` sont sécurisées, et la valeur reste inchangée.  
  
 Un objet de type flottant peut également être converti en type moins précis, s'il se trouve dans une plage qui peut être représentée par ce type.  \(Consultez [Limites de flottement](../cpp/floating-limits.md) pour les plages des types flottants.\) Si la valeur d'origine ne peut pas être représentée précisément, elle peut être convertie à la valeur représentable inférieure ou supérieure suivante.  Si aucune valeur de ce type n'existe, le résultat n'est pas défini.  Prenons l'exemple suivant :  
  
```  
cout << (float)1E300 << endl;  
```  
  
 La valeur maximale représentable par le type **float** est 3.402823466E38. Il s'agit d'un nombre largement inférieur à 1E300.  Par conséquent, le nombre est converti à l'infini et le résultat est 1.\#INF.  
  
## Conversions entre types intégraux et à virgule flottante  
 Certaines expressions peuvent provoquer la conversion des objets de type flottant en types intégraux, ou vice versa.  Lorsqu'un objet de type intégral est converti en type flottant et que la valeur d'origine ne peut pas être représentée précisément, elle peut être convertie à la valeur représentable inférieure ou supérieure suivante.  
  
 Lorsqu'un objet de type flottant est converti en type intégral, la partie fractionnaire est tronquée.  Aucun arrondi n'est effectué pendant le processus de conversion.  La troncation signifie par exemple que le nombre 1,3 est converti en 1 et –1,3 est converti en –1.  
  
## Conversions arithmétiques  
 De nombreux opérateurs binaires \(présentés dans [Expressions avec des opérateurs binaires](../cpp/expressions-with-binary-operators.md)\) effectuent les conversions d'opérandes et génèrent les résultats de la même façon.  La façon dont ces opérateurs effectuent les conversions s'appelle « conversions arithmétiques habituelles ». Les conversions arithmétiques des opérandes de différents types natifs sont exécutées comme indiqué dans le tableau suivant.  Les types typedef se comportent selon leurs types natifs sous\-jacents.  
  
### Conditions pour la conversion de type  
  
|Conditions remplies|Conversion|  
|-------------------------|----------------|  
|L'un des opérandes est du type **long double**.|L'autre opérande est converti en type **long double**.|  
|Condition précédente non remplie et l'un des opérandes est de type **double**.|L'autre opérande est converti en type **double**.|  
|Conditions précédentes non remplies et l'un des opérandes est de type **float**.|L'autre opérande est converti en type **float**.|  
|Conditions précédentes non remplies \(aucun des opérandes n'est de type flottant\).|Les promotions intégrales sont exécutées sur les opérandes comme suit :<br /><br /> -   Si l'un des opérandes est de type `unsigned` **long**, l'autre opérande est converti en type `unsigned long`.<br />-   Si la condition précédente n'est pas remplie et que l'un des opérandes est de type **long** et l'autre de type `unsigned` `int`, les deux opérandes sont convertis en type `unsigned long`.<br />-   Si les deux conditions précédentes ne sont pas réunies et que l'un des opérandes est de type **long**, l'autre opérande est converti en type **long**.<br />-   Si les trois conditions précédentes ne sont pas réunies et que l'un des opérandes est de type `unsigned int`, l'autre opérande est converti en type `unsigned int`.<br />-   Si aucune des conditions précédentes n'est remplie, les deux opérandes sont convertis en type `int`.|  
  
 Le code suivant illustre les règles de conversion décrites dans le tableau :  
  
```  
// arithmetic_conversions.cpp  
double dVal;  
float fVal;  
int iVal;  
unsigned long ulVal;  
  
int main() {  
   // iVal converted to unsigned long  
   // result of multiplication converted to double  
   dVal = iVal * ulVal;  
  
   // ulVal converted to float  
   // result of addition converted to double  
   dVal = ulVal + fVal;  
}  
```  
  
 Dans l'exemple précédent, la première instruction affiche la multiplication de deux types intégraux, `iVal` et `ulVal`.  La condition remplie est que ni l'un ni l'autre opérande n'est de type flottant et qu'un opérande est de type `unsigned int`.  Par conséquent, l'autre opérande, `iVal`, est converti en type `unsigned int`.  Le résultat est assigné à `dVal`.  La condition remplie est qu'un opérande est de type **double**. Par conséquent, le résultat `unsigned int` de la multiplication est converti en type **double**.  
  
 Dans l'exemple précédent, la deuxième instruction montre l'ajout d'un type **float** et d'un type intégral, `fVal` et `ulVal`.  La variable `ulVal` est convertie en type **float** \(troisième condition dans le tableau\).  Le résultat de l'addition est converti en type **double** \(seconde condition dans le tableau\) et assigné à `dVal`.  
  
## Conversions de pointeurs  
 Les pointeurs peuvent être convertis durant l'assignation, l'initialisation, la comparaison et d'autres expressions.  
  
### Pointeur vers classes  
 Il existe deux cas dans lesquels un pointeur vers une classe peut être converti en un pointeur vers une classe de base.  
  
 Dans le premier cas, la classe de base spécifiée est accessible et la conversion est n'est pas ambiguë.  \(Consultez [Classes de base multiples](../cpp/multiple-base-classes.md) pour plus d'informations sur les références de classe de base ambiguës.\)  
  
 L'accessibilité d'une classe de base dépend du type d'héritage utilisé dans la dérivation.  Prenons l'héritage illustré dans l'illustration suivante.  
  
 ![Accessibilité de la classe de base d'un graphique d'héritage](../cpp/media/vc38xa1.png "vc38XA1")  
Graphique d'héritage pour l'illustration de l'accessibilité de la classe de base  
  
 Le tableau suivant indique l'accessibilité de la classe de base d'après la situation illustrée.  
  
### Accessibilité de la classe de base  
  
|Type de fonction|Dérivation|Conversion de<br /><br /> B\* à A\* autorisé ?|  
|----------------------|----------------|--------------------------------------------|  
|Fonction externe \(hors portée de classe\)|Privé|Non|  
||Protected|Non|  
||Public|Oui|  
|Fonction membre B \(dans la portée B\)|Privé|Oui|  
||Protected|Oui|  
||Public|Oui|  
|Fonction membre C \(dans la portée C\)|Privé|Non|  
||Protected|Oui|  
||Public|Oui|  
  
 Dans le second cas, un pointeur vers une classe peut être converti en pointeur vers une classe de base lorsque vous utilisez une conversion de type explicite.  \(Pour plus d'informations sur les conversions de type explicite, consultez [Expressions avec conversions de type explicite](http://msdn.microsoft.com/fr-fr/060ad6b4-9592-4f3e-8509-a20ac84a85ae).\)  
  
 Le résultat de ce type de conversion est un pointeur vers le « sous\-objet », la partie de l'objet qui est complètement décrite par la classe de base.  
  
 Le code suivant définit deux classes, `A` et `B`, où `B` est dérivée de `A`.  \(Pour plus d'informations sur l'héritage, consultez [Classes dérivées](../cpp/inheritance-cpp.md).\) Il définit ensuite `bObject`, un objet de type `B`, et deux pointeurs \(`pA` et `pB`\) qui pointent vers l'objet.  
  
```  
// conve__pluslang_Pointers_to_Classes.cpp  
// C2039 expected  
class A  
{  
public:  
    int AComponent;  
    int AMemberFunc();  
};  
  
class B : public A  
{  
public:  
    int BComponent;  
    int BMemberFunc();  
};  
int main()  
{  
   B bObject;  
   A *pA = &bObject;  
   B *pB = &bObject;  
  
   pA->AMemberFunc();   // OK in class A  
   pB->AMemberFunc();   // OK: inherited from class A  
   pA->BMemberFunc();   // Error: not in class A  
}  
```  
  
 Le pointeur `pA` est de type `A *`, ce qui peut être interprété comme suit : « pointeur vers un objet de type `A` ». Les membres de `bObject` `(`tels que `BComponent` et `BMemberFunc`\) sont propres au type `B` et sont donc inaccessibles via `pA`.  Le pointeur `pA` autorise l'accès uniquement aux caractéristiques \(fonctions membres et données\) de l'objet définies dans la classe `A`.  
  
### Pointeur vers fonction  
 Un pointeur vers une fonction peut être converti en type **void \***, si le type **void \*** est assez grand pour contenir ce pointeur.  
  
### Pointeur vers void  
 Les pointeurs vers le type `void` peuvent être convertis en pointeurs vers tout autre type, mais uniquement avec un cast de type explicite \(contrairement à ce qui se passe en C\).  \(Consultez [Expressions avec conversions de type explicite](http://msdn.microsoft.com/fr-fr/060ad6b4-9592-4f3e-8509-a20ac84a85ae) pour plus d'informations sur les casts de type.\) Un pointeur vers n'importe quel type peut être converti implicitement en pointeur vers le type `void`. Un pointeur vers un objet incomplet d'un type peut être converti en pointeur vers `void` \(implicitement\) et inversement \(explicitement\).  Le résultat de ce type de conversion est égal à la valeur du pointeur d'origine.  Un objet est considéré incomplet s'il est déclaré, mais que les informations sont insuffisantes pour déterminer sa taille ou sa classe de base.  
  
 Un pointeur vers tout objet qui n'est pas **const** ou `volatile` peut être converti implicitement en un pointeur de type **void \***.  
  
### Pointeurs const et volatile  
 C\+\+ ne fournit pas de conversion standard à partir d'un type **const** ou `volatile` vers un type qui n'est pas **const** ou `volatile`.  Cependant, toute sorte de conversion peut être spécifiée à l'aide de casts de type explicite \(y compris les conversions qui ne sont pas sécurisées\).  
  
> [!NOTE]
>  Les pointeurs C\+\+ vers des membres, à l'exception des pointeurs vers des membres statiques, sont différents des pointeurs normaux et n'ont pas les mêmes conversions standard.  Les pointeurs vers des membres statiques sont des pointeurs normaux et ils ont les mêmes conversions que les pointeurs normaux.  \(Consultez [\(NOTINBUILD\) Directly Derived Types](http://msdn.microsoft.com/fr-fr/d2d611d1-dbff-4fb4-9858-e1572544f5c3) pour plus d'informations.\)  
  
### Conversions de pointeurs null  
 Une expression constante intégrale qui correspond à zéro ou cette expression casté en un type pointeur, est convertie en un pointeur appelé pointeur null. Ce pointeur est assuré de ne pas être considéré comme égal à un pointeur désignant un objet ou une fonction valide quelconque \(à l'exception des pointeurs désignant des objets basés, qui peuvent avoir le même décalage et pointer néanmoins sur des objets différents\).  
  
 En C\+\+11, le type [nullptr](../cpp/nullptr.md) doit être préféré au pointeur null de style C.  
  
### Conversions d'expression de pointeur  
 Toute expression avec un type de tableau peut être convertie en un pointeur du même type.  Le résultat de la conversion est un pointeur vers le premier élément du tableau.  L'exemple suivant illustre cette conversion :  
  
```  
char szPath[_MAX_PATH]; // Array of type char.  
char *pszPath = szPath; // Equals &szPath[0].  
```  
  
 Une expression qui entraîne une fonction qui retourne un type particulier est convertie en un pointeur vers une fonction qui retourne ce type, sauf lorsque :  
  
-   L'expression est utilisée comme un opérande de l'opérateur d'adresse \(**&**\).  
  
-   L'expression est utilisée comme opérande de l'opérateur d'appel de fonction.  
  
## Conversions de références  
 Une référence à une classe peut être convertie en une référence à une classe de base dans les cas suivants :  
  
-   La classe de base spécifiée est accessible \(comme défini dans [Pointeurs désignant des classes](../misc/pointers-to-classes.md)\).  
  
-   La conversion n'est pas ambiguë.  \(Consultez [Classes de base multiples](../cpp/multiple-base-classes.md) pour plus d'informations sur les références de classe de base ambiguës.\)  
  
 Le résultat de la conversion est un pointeur vers le sous\-objet qui représente la classe de base.  
  
## Pointeur vers membre  
 Les pointeurs vers des membres de classe peuvent être convertis durant l'assignation, l'initialisation, la comparaison et d'autres expressions.  Cette section décrit les conversions de pointeur vers membre suivantes :  
  
## Pointeur vers membre de classe de base  
 Un pointeur vers un membre d'une classe de base peut être converti en un pointeur vers un membre d'une classe dérivée de cette classe lorsque les conditions suivantes sont remplies :  
  
-   La conversion inverse, du pointeur vers la classe dérivée vers le pointeur de classe de base, est accessible.  
  
-   La classe dérivée n'hérite pratiquement pas de la classe de base.  
  
 Lorsque l'opérande gauche est un pointeur vers membre, l'opérande droite doit être de type pointeur vers membre ou une expression constante qui correspond à 0.  Cette assignation est valide uniquement dans les cas suivants :  
  
-   L'opérande droite est un pointeur vers un membre de la même classe que l'opérande gauche.  
  
-   L'opérande gauche est un pointeur vers un membre d'une classe dérivée de façon publique et non ambiguë de la classe de l'opérande droite.  
  
## Conversions de constantes intégrales  
 Une expression constante intégrale qui correspond à la valeur zéro est convertie en un pointeur appelé « pointeur null ». Ce pointeur est assuré de ne pas être considéré comme égal à un pointeur désignant un objet ou une fonction valide quelconque \(à l'exception des pointeurs désignant des objets basés, qui peuvent avoir le même décalage et pointer néanmoins sur des objets différents\).  
  
 Le code suivant illustre la définition d'un pointeur désignant le membre `i` dans la classe `A`.  Le pointeur, `pai`, est initialisé à 0, qui est le pointeur null.  
  
```  
// conve__pluslang_Integral_Constant_Expressions.cpp  
class A  
{  
public:  
 int i;  
};  
  
int A::*pai = 0;  
  
int main()  
{  
}  
```  
  
## Voir aussi  
 [Référence du langage C\+\+](../cpp/cpp-language-reference.md)