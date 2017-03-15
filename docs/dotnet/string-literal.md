---
title: "Litt&#233;ral de cha&#238;ne | Microsoft Docs"
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
helpviewer_keywords: 
  - "littéraux de chaîne"
  - "chaînes (C++), littéraux de chaîne"
ms.assetid: 6d1fc3f8-0d58-4d68-9678-16b4f6dc4766
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Litt&#233;ral de cha&#238;ne
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La gestion des littéraux de chaîne a changé entre Extensions managées pour C\+\+ et [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  
  
 Dans la conception du langage des Extensions managées pour C\+\+, un littéral de chaîne managé était indiqué en préfaçant d'un `S` le littéral de chaîne.  Par exemple :  
  
```  
String *ps1 = "hello";  
String *ps2 = S"goodbye";  
```  
  
 Les charges mémoire en termes de performances entre les deux initialisations s'avèrent non négligeables, comme le montre la représentation CIL suivante à partir de **ildasm**:  
  
```  
// String *ps1 = "hello";  
ldsflda    valuetype $ArrayType$0xd61117dd  
     modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier)   
     '?A0xbdde7aca.unnamed-global-0'  
  
newobj instance void [mscorlib]System.String::.ctor(int8*)  
stloc.0  
  
// String *ps2 = S"goodbye";  
ldstr      "goodbye"  
stloc.0  
```  
  
 Cela représente une économie tout à fait intéressante en contrepartie d'un effort minime, qui consiste simplement à se rappeler \(ou à apprendre\) de préfixer une chaîne littérale avec un `S`.  Dans la nouvelle syntaxe, la gestion des littéraux de chaîne est rendue transparente et déterminée par le contexte d'utilisation.  Le `S` ne doit plus nécessairement être spécifié.  
  
 Que se passe t\-il dans les cas où le compilateur doit être dirigé explicitement vers une interprétation ou une autre ?  Dans ces cas, il faut appliquer un cast explicite.  Par exemple :  
  
```  
f( safe_cast<String^>("ABC") );  
```  
  
 De plus, le littéral de chaîne fait désormais correspondre une `String` à une simple conversion plutôt qu'à une conversion standard.  Bien que cela puisse sembler peu de choses, cela modifie la résolution des jeux de fonctions surchargés qui incluent une `String` et un `const char*` en tant que paramètres formels en concurrence.  La résolution qui jusqu'ici se résolvait en une instance `const char*` est désormais signalée comme ambiguë.  Par exemple :  
  
```  
ref struct R {  
   void f(const char*);  
   void f(String^);  
};  
  
int main () {  
   R r;  
   // old syntax: f( const char* );  
   // new syntax: error: ambiguous  
   r.f("ABC");   
}  
```  
  
 Pourquoi y a\-t\-il une différence ?  Puisque l'on se trouve face à plusieurs instances nommées `f` existant au sein du programme, il faut appliquer à l'appel l'algorithme de la résolution de la surcharge de la fonction.  La résolution formelle d'une fonction de surcharge implique trois étapes.  
  
1.  La collection des fonctions candidates.  Les fonctions candidates sont des méthodes comprises dans la portée qui correspondent de façon lexicale au nom de la fonction appelée.  Par exemple, puisque `f()` est appelée à travers une instance de `R`, toutes les fonctions nommées `f` qui ne sont pas un membre de `R` \(ou de sa hiérarchie de classe de base\) ne sont pas des fonctions candidates.  Notre exemple montre deux fonctions candidates.  Ce sont les deux fonctions membres de `R` nommées `f`.  Un appel échoue au cours de cette phase si le jeu de fonctions candidates est vide.  
  
2.  Le jeu de fonctions viables parmi les fonctions candidates.  Une fonction viable est une fonction qui peut être appelée avec les arguments spécifiés dans l'appel, connaissant le nombre et le type des arguments.  Dans notre exemple, les fonctions candidates sont également des fonctions viables.  Un appel échoue au cours de cette phase si le jeu de fonctions viables est vide.  
  
3.  Sélectionnez la fonction qui constitue la meilleure correspondance avec l'appel.  Cela se fait en classant les conversions appliquées pour transformer le type des arguments en type des paramètres de fonctions viables.  Cette procédure est relativement directe dans le cas d'une fonction à un seul paramètre, mais se complique quelque peu en présence de plusieurs paramètres.  Un appel échoue lors de cette phase s'il n'existe aucune meilleure correspondance.  Autrement dit, si les conversions nécessaires pour transformer le type de l'argument réel en type du paramètre formel sont également satisfaisantes.  L'appel est signalé comme étant ambigu.  
  
 Dans les Extensions managées, la résolution de cet appel appelait l'instance `const char*` comme étant la meilleure correspondance.  Dans la nouvelle syntaxe, les conversions nécessaires pour faire correspondre `"abc"` à `const char*` et `String^` sont désormais équivalentes, c'est\-à\-dire également correctes \- et l'appel est donc signalé comme incorrect \- autrement dit, ambigu.  
  
 Cela soulève deux questions :  
  
-   Quel est le type de l'argument réel, `"abc"` ?  
  
-   Quel est l'algorithme servant à déterminer si une conversion de type est meilleure qu'une autre ?  
  
 Le type du littéral de chaîne `"abc"` est `const char[4]` \- souvenez\-vous, il y a un caractère de terminaison nul implicite à la fin de chaque littéral de chaîne.  
  
 L'algorithme servant à déterminer si une conversion de type est meilleure qu'une autre implique que les conversions de types possibles soient placées dans une hiérarchie.  Voici comment je comprends cette hiérarchie \- toutes ces conversions étant, bien sûr, implicites.  L'utilisation d'une notation de cast explicite substitue la hiérarchie de la même façon que les parenthèses substituent la priorité habituelle des opérateurs d'une expression.  
  
1.  Une correspondance exacte représente la meilleure solution.  Curieusement, un argument n'a pas besoin de correspondre exactement au type du paramètre pour constituer une correspondance exacte ; il suffit qu'il en soit assez proche.  Ceci est essentiel pour comprendre ce qui se passe dans cet exemple et saisir en quoi le langage a changé.  
  
2.  Une promotion est préférable à une conversion standard.  Par exemple, promouvoir un `short int` au rang de `int` est meilleur que de convertir un `int` en un `double`.  
  
3.  Une conversion standard est préférable à une conversion boxing.  Par exemple, la conversion d'un `int` en un `double` est meilleure que la conversion boxing d'un `int` en un `Object`.  
  
4.  Une conversion boxing est préférable à une conversion implicite définie par l'utilisateur.  Par exemple, il est préférable d'effectuer une conversion boxing d'un `int` en un `Object` plutôt que d'appliquer un opérateur de conversion d'une classe de valeur `SmallInt`.  
  
5.  Une conversion implicite définie par l'utilisateur est préférable à une absence totale de conversion.  Une conversion implicite définie par l'utilisateur représente la dernière chance avant l'Erreur \(en étant toutefois prévenu que la signature formelle peut contenir un tableau de paramètres ou des points de suspension à cet emplacement\).  
  
 Ainsi, que signifie la formule selon laquelle une correspondance exacte n'est pas toujours exactement une correspondance ?  Par exemple, `const char[4]` ne correspond pas exactement à `const char*` ni à `String^` et pourtant l'ambiguïté de notre exemple concerne deux correspondances exactes en conflit \!  
  
 En réalité, une correspondance exacte comprend plusieurs conversions ordinaires.  Sous ISO\-C\+\+, il existe quatre conversions ordinaires qui peuvent s'appliquer tout en méritant encore la qualification de correspondance exacte.  Trois d'entre elles sont connues sous le nom de transformations lvalue.  Le quatrième type est appelé conversion de qualification.  Les trois transformations lvalue sont traitées comme une meilleure correspondance exacte que celles qui nécessitent une conversion de qualification.  
  
 Une des formes des transformations lvalue est la conversion tableau natif en pointeur.  C'est ce qu'implique la correspondance entre un `const char[4]` et `const char*`.  Par conséquent, la correspondance entre `f("abc")` et `f(const char*)` est une correspondance exacte.  Dans les premières versions de notre langage, ceci était en réalité la meilleure correspondance.  
  
 Pour que le compilateur signale l'appel comme ambigu, il faut donc que la conversion d'un `const char[4]` en une `String^` soit également une correspondance exacte via une conversion ordinaire.  C'est cette modification qui a été introduite dans la nouvelle version du langage.  Et c'est pourquoi l'appel est désormais signalé comme ambigu.  
  
## Voir aussi  
 [Modification d'ordre général apportée au langage](../dotnet/general-language-changes-cpp-cli.md)   
 [String](../windows/string-cpp-component-extensions.md)