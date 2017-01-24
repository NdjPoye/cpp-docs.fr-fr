---
title: "switch, instruction (C++) | Microsoft Docs"
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
  - "default"
  - "default_cpp"
  - "switch"
  - "switch_cpp"
  - "case"
  - "case_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "case (mot clé) (C++), dans des instructions switch"
  - "default (mot clé) (C++)"
  - "switch (mot clé) (C++)"
ms.assetid: 6c3f3ed3-5593-463c-8f4b-b33742b455c6
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# switch, instruction (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Autorise la sélection parmi plusieurs sections de code, selon la valeur d'une expression intégrale.  
  
## Syntaxe  
  
```  
  
      switch ( expression )  
   case constant-expression : statement  
   [default  : statement]  
```  
  
## Notes  
 *expression* doit être de type intégral ou d'un type de classe pour lequel il existe une conversion non ambiguë en type intégral.  La promotion d'un intégral est exécutée comme décrit dans [Promotions d'un intégral](../misc/integral-promotions.md).  
  
 Le corps de l'instruction `switch` se compose d'une série d'étiquettes **case** et d'une étiquette facultative **default**.  Deux expressions constantes dans des instructions **case** ne peuvent pas avoir la même valeur.  L'étiquette **default** ne peut apparaître qu'une seule fois.  Les instructions étiquetées ne sont pas des exigences syntaxiques, mais sans elles l'instruction `switch` n'a pas de sens.   L'instruction par défaut n'a pas besoin d'être à la fin ; elle peut apparaître n'importe où dans le corps de l'instruction switch.  Une étiquette case ou default ne peut apparaître que dans une instruction switch.  
  
 *constant\-expression* de chaque **case** est converti vers le type de *expression* et comparé à *expression* en matière d'égalité.  Le contrôle est passé à l'instruction dont **case** *constant\-expression* correspond à la valeur de *expression*.  Le comportement résultant est indiqué dans le tableau suivant.  
  
### Comportement de l'instruction switch  
  
|Condition|Action|  
|---------------|------------|  
|La valeur convertie correspond à celle de l'expression de contrôle promue.|Le contrôle est transféré à l'instruction qui suit cette étiquette.|  
|Aucune des constantes ne correspond aux constantes des étiquettes **case** ; une étiquette **default** est présente.|Le contrôle est transféré vers l'étiquette **default**.|  
|Aucune des constantes ne correspond aux constantes des étiquettes **case** ; l'étiquette **default** n'est pas présente.|Le contrôle est transféré à l'instruction, après l'exécution de l'instruction `switch`.|  
  
 Si une expression correspondante est trouvée, le contrôle n'est pas bloqué par les étiquettes **case** ou **default**.  L'instruction [break](../cpp/break-statement-cpp.md) est utilisée pour arrêter l'exécution et transférer le contrôle à l'instruction située après l'instruction `switch`.  Sans instruction **break**, chaque instruction de l'étiquette correspondante **case** à la fin de `switch`, y compris **default**, est exécutée.  Par exemple :  
  
```  
// switch_statement1.cpp  
#include <stdio.h>  
  
int main() {  
   char *buffer = "Any character stream";  
   int capa, lettera, nota;  
   char c;  
   capa = lettera = nota = 0;  
  
   while ( c = *buffer++ )   // Walks buffer until NULL  
   {  
      switch ( c )  
      {  
         case 'A':  
            capa++;  
            break;  
         case 'a':  
            lettera++;  
            break;  
         default:  
            nota++;  
      }  
   }  
   printf_s( "\nUppercase a: %d\nLowercase a: %d\nTotal: %d\n",  
      capa, lettera, (capa + lettera + nota) );  
}  
```  
  
 Dans l'exemple ci\-dessus, `capa` est incrémenté si `c` est un `A` majuscule.  L'instruction `break` après `capa++` arrête l'exécution du corps de l'instruction `switch`, et le contrôle passe à la boucle `while`.  Sans l'instruction `break`, `lettera` et `nota` seraient également incrémentés.  Un objectif similaire est réalisé par l'instruction `break` pour `case 'a'`.  Si `c` est une minuscule `a`, `lettera` est incrémenté et l'instruction `break` termine le corps de l'instruction `switch`.  Si `c` n'est pas `a` ou `A`, l'instruction `default` est exécutée.  
  
 Un bloc interne d'une instruction `switch` peut contenir des définitions avec des initialisations tant qu'elles sont accessibles, c'est\-à\-dire non contournées par tous les chemins d'exécution possibles.  Les noms présentés à l'aide de ces déclarations ont une portée locale.  Par exemple :  
  
```  
// switch_statement2.cpp  
// C2360 expected  
#include <iostream>  
using namespace std;  
int main(int argc, char *argv[])  
{  
   switch( tolower( *argv[1] ) )  
   {  
       // Error. Unreachable declaration.  
       char szChEntered[] = "Character entered was: ";  
  
   case 'a' :  
       {  
       // Declaration of szChEntered OK. Local scope.  
       char szChEntered[] = "Character entered was: ";  
       cout << szChEntered << "a\n";  
       }  
       break;  
  
   case 'b' :  
       // Value of szChEntered undefined.  
       cout << szChEntered << "b\n";  
       break;  
  
   default:  
       // Value of szChEntered undefined.  
       cout << szChEntered << "neither a nor b\n";  
       break;  
   }  
}  
```  
  
 Une instruction `switch` peut être imbriquée.  Dans ces cas, les étiquettes **case** ou **default** s'associent à l'instruction `switch` la plus proche qui les entoure.  
  
## Section spécifique à Microsoft  
 Microsoft C ne limite pas le nombre de valeurs de cas dans une instruction `switch`.  Le nombre est limité uniquement par la mémoire disponible.  C ANSI requiert qu'au moins 257 étiquettes soient autorisées dans une instruction `switch`.  
  
 Par défaut pour Microsoft C, les extensions Microsoft sont activées.  Utilisez l'option du compilateur [\/Za](../build/reference/za-ze-disable-language-extensions.md) pour désactiver ces extensions.  
  
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [Instructions de sélection](../cpp/selection-statements-cpp.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [\(NOTINBUILD\) Using Labels in the case Statement](http://msdn.microsoft.com/fr-fr/a6ff057d-1aee-42ed-a28d-ee6a565b3197)