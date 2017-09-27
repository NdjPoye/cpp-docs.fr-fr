---
title: "commutateur d’instruction (C++) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- default
- default_cpp
- switch
- switch_cpp
- case
- case_cpp
dev_langs:
- C++
helpviewer_keywords:
- switch keyword [C++]
- case keyword [C++], in switch statements
- default keyword [C++]
ms.assetid: 6c3f3ed3-5593-463c-8f4b-b33742b455c6
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
ms.openlocfilehash: 5e05299d88cadfafb9ccb7523aac33096b90d46b
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="switch-statement-c"></a>switch, instruction (C++)
Autorise la sélection parmi plusieurs sections de code, selon la valeur d'une expression intégrale.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
   switch ( init; expression )  
   case constant-expression : statement  
   [default  : statement]  
```  
  
## <a name="remarks"></a>Remarques  
 Le *expression* doit être de type intégral ou d’un type de classe pour laquelle il existe une conversion non ambiguë en type intégral. La promotion intégrale est exécutée comme décrit dans [Conversions Standard](standard-conversions.md).  
  
 Le `switch` corps d’instruction se compose d’une série de **cas** étiquettes et éventuellement un **par défaut** étiquette. Aucun deux expressions constantes dans **cas** instructions peuvent correspondre à la même valeur. Le **par défaut** étiquette peut apparaître qu’une seule fois. Les instructions étiquetées ne sont pas des exigences syntaxiques, mais sans elles l'instruction `switch` n'a pas de sens.   L'instruction par défaut n'a pas besoin d'être à la fin ; elle peut apparaître n'importe où dans le corps de l'instruction switch. Une étiquette case ou default ne peut apparaître que dans une instruction switch.  
  
 Le *expression constante* dans chaque **cas** est converti vers le type de *expression* et comparé *expression* pour égalité. Contrôle passe à l’instruction dont **cas** *expression constante* correspond à la valeur de *expression*. Le comportement résultant est indiqué dans le tableau suivant.  
  
### <a name="switch-statement-behavior"></a>Comportement de l'instruction switch  
  
|Condition|Action|  
|---------------|------------|  
|La valeur convertie correspond à celle de l'expression de contrôle promue.|Le contrôle est transféré à l'instruction qui suit cette étiquette.|  
|Aucune des constantes correspond à l’une des constantes dans le **cas** étiquettes ; un **par défaut** étiquette n’est présente.|Le contrôle est transféré à la **par défaut** étiquette.|  
|Aucune des constantes correspond à l’une des constantes dans le **cas** étiquettes ; **par défaut** étiquette n’est pas présente.|Le contrôle est transféré à l'instruction, après l'exécution de l'instruction `switch`.|  
  
 Si une expression correspondante est trouvée, le contrôle n’est pas bloqué par les **cas** ou **par défaut** étiquettes. Le [saut](../cpp/break-statement-cpp.md) instruction est utilisée pour arrêter l’exécution et de transférer le contrôle à l’instruction après la `switch` instruction. Sans un **saut** chaque instruction, à partir de la mise en correspondance **cas** étiquette à la fin de la `switch`, y compris le **par défaut**, est exécutée. Exemple :  
  
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
  
 Dans l'exemple ci-dessus, `capa` est incrémenté si `c` est un `A` majuscule. L'instruction `break` après `capa++` arrête l'exécution du corps de l'instruction `switch`, et le contrôle passe à la boucle `while`. Sans le `break` instruction, l’exécution serait « passer » à l’instruction étiquetée, afin que `lettera` et `nota` seraient également incrémentés. Un objectif similaire est réalisé par l'instruction `break` pour `case 'a'`. Si `c` est une minuscule `a`, `lettera` est incrémenté et l'instruction `break` termine le corps de l'instruction `switch`. Si `c` n'est pas `a` ou `A`, l'instruction `default` est exécutée.  

 **Visual Studio 2017 et versions ultérieur :** (disponible avec [/std : c ++ 17](../build/reference/std-specify-language-standard-version.md)) le `[[fallthrough]]` attribut est spécifié dans la norme C ++ 17. Il peut être utilisé dans un `switch` instruction en tant qu’indicateur du compilateur (ou à toute personne lisant le code), ce comportement passage est destiné. Le compilateur Visual C++ n’avertit actuellement pas sur le comportement de fallthrough, afin de cet attribut n’a aucun comportement de compilateur d’effet. Notez que l’attribut est appliqué à une instruction vide au sein de l’instruction étiquetée ; en d’autres termes, le point-virgule est nécessaire.

```cpp
int main()
{
    int n = 5;
    switch (n)
    {

    case 1:
        a();
        break;
    case 2:
        b();
        d();
        [[fallthrough]]; // I meant to do this!
    case 3:
        c();
        break;
    default:
        d();
        break;
    }

    return 0;
}
```

 **Visual Studio 2017 15,3 et versions ultérieures** (disponible avec [/std : c ++ 17](../build/reference/std-specify-language-standard-version.md)) : une instruction switch peut introduire et initialiser une variable dont la portée est limitée au bloc de l’instruction switch :

```cpp
 switch (Gadget gadget(args); auto s = gadget.get_status())
        {
        case status::good:
            gadget.zip();
            break;
        case status::bad:
            throw BadGadget();
        };
```

 Un bloc interne d'une instruction `switch` peut contenir des définitions avec des initialisations tant qu'elles sont accessibles, c'est-à-dire non contournées par tous les chemins d'exécution possibles. Les noms présentés à l'aide de ces déclarations ont une portée locale. Exemple :  
  
```cpp  
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
  
 Une instruction `switch` peut être imbriquée. Dans ce cas, **cas** ou **par défaut** étiquettes associer le plus proche `switch` instruction qui les entoure.  

 
## <a name="microsoft-specific"></a>Section spécifique à Microsoft  
 Microsoft C ne limite pas le nombre de valeurs de cas dans une instruction `switch`. Le nombre est limité uniquement par la mémoire disponible. C ANSI requiert qu'au moins 257 étiquettes soient autorisées dans une instruction `switch`.  
  
 Par défaut pour Microsoft C, les extensions Microsoft sont activées. Utilisez le [/Za](../build/reference/za-ze-disable-language-extensions.md) option du compilateur pour désactiver ces extensions.  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Instructions de sélection](../cpp/selection-statements-cpp.md)   
 [Mots clés](../cpp/keywords-cpp.md)   
 
