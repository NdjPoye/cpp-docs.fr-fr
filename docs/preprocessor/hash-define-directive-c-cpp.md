---
title: "#define, directive (C/C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "#define"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#define (directive)"
  - "#define (directive), syntaxe"
  - "directive define (#define)"
  - "directive define (#define), syntaxe"
  - "préprocesseur, directives"
ms.assetid: 33cf25c6-b24e-40bf-ab30-9008f0391710
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# #define, directive (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`#define` crée une *macro*, qui est l'association d'un identificateur ou d'un identificateur paramétré avec une chaîne de jeton.  Une fois la macro définie, le compilateur peut substituer la chaîne de jeton pour chaque occurrence de l'identificateur dans le fichier source.  
  
## Syntaxe  
 `#define` *identifier* *token\-string*facultatif  
  
 `#define` *identifier*`(` *identifier*facultatif`,` *...* `,` *identifier*facultatif `)` *token\-string*facultatif  
  
## Notes  
 La directive `#define` oblige le compilateur à substituer *token\-string* pour chaque occurrence de *identifier* dans le fichier source.  *identifier* est remplacé uniquement lorsqu'il forme un jeton.  En d'autres termes, *identifier* n'est pas remplacé s'il apparaît dans un commentaire, dans une chaîne ou dans un identificateur plus long.  Pour plus d'informations, consultez [Jetons C\+\+](../cpp/tokens-cpp.md).  
  
 L'argument *token\-string* se compose d'une série de jetons, tels que les mots clés, les constantes ou les instructions complètes.  Un ou plusieurs espaces blancs doivent séparer *token\-string* de *identifier*.  Cet espace blanc n'est pas considéré comme faisant partie du texte substitué, pas plus que tout espace blanc qui suit le dernier jeton du texte.  
  
 Un `#define` sans *token\-string* supprime les occurrences de *identifier* du fichier source.  *identifier* reste défini et peut être testé à l'aide des directives `#if defined` et `#ifdef`.  
  
 La deuxième forme de syntaxe définit une macro de type fonction avec des paramètres.  Cette forme accepte la liste facultative des paramètres qui doivent apparaître entre parenthèses.  Une fois la macro définie, chaque occurrence suivante de *identifier*\( *identifier*facultatif,…, *identifier*facultatif\) est remplacée par une version de l'argument *token\-string* dont les arguments réels sont remplacés par des paramètres formels.  
  
 Les noms des paramètres formels apparaissent dans *token\-string* pour marquer les emplacements où des valeurs réelles sont substituées.  Chaque nom de paramètre peut apparaître plusieurs fois dans *token\-string*, et les noms peuvent apparaître dans n'importe quel ordre.  Le nombre d'arguments de l'appel doit correspondre au nombre de paramètres de la définition de macro.  L'utilisation répandue des parenthèses garantit que les arguments réels complexes sont interprétés correctement.  
  
 Les paramètres formels de la liste sont séparés par des virgules.  Chaque nom contenu dans la liste doit être unique et la liste doit être placée entre parenthèses.  Aucun espace ne peut séparer *identifier* de la parenthèse ouvrante.  Utilisez la concaténation de ligne : placez une barre oblique inverse \(`\`\) immédiatement avant le caractère de saut de ligne pour les longues directives sur plusieurs lignes de code source.  La portée d'un nom de paramètre formel s'étend jusqu'à la nouvelle ligne qui termine *token\-string*.  
  
 Lorsqu'une macro a été définie dans la deuxième forme de syntaxe, les instances textuelles suivantes suivies d'une liste d'arguments indiquent un appel de macro.  Les arguments réels qui suivent une instance de *identifier* dans le fichier source sont comparés aux paramètres formels correspondants dans la définition de macro.  Chaque paramètre formel présent dans *token\-string* qui n'est pas précédé par un opérateur de transformation en chaîne \(`#`\), de charizing \(`#@`\), ou de collage de jeton \(`##`\), ou n'est pas suivi d'un opérateur `##`, est remplacé par l'argument réel correspondant.  Toutes les macros figurant dans l'argument réel sont développées avant que la directive ne remplace le paramètre formel. \(Les opérateurs sont décrits dans [Opérateurs de préprocesseur](../preprocessor/preprocessor-operators.md).\)  
  
 Les exemples suivants de macros comportant des arguments illustrent la deuxième forme de la syntaxe `#define` :  
  
```  
// Macro to define cursor lines   
#define CURSOR(top, bottom) (((top) << 8) | (bottom))  
  
// Macro to get a random integer with a specified range   
#define getrandom(min, max) \  
    ((rand()%(int)(((max) + 1)-(min)))+ (min))  
```  
  
 Les arguments avec des effets secondaires provoquent des résultats inattendus générés par les macros.  Un paramètre formel donné peut apparaître plusieurs fois dans *token\-string*.  Si ce paramètre formel est remplacé par une expression à effets secondaires, l'expression, avec ses effets secondaires, peut être évaluée plusieurs fois. \(Consultez les exemples dans [Collage de jeton \(\#\#\), opérateur](../preprocessor/token-pasting-operator-hash-hash.md).\)  
  
 La directive `#undef` entraîne l'oubli de la définition de préprocesseur d'un identificateur.  Pour plus d'informations, consultez [Directive \#undef](../preprocessor/hash-undef-directive-c-cpp.md).  
  
 Si le nom de la macro définie apparaît dans *token\-string* \(même comme résultat d'une autre expansion macro\), il n'est pas développé.  
  
 Un deuxième `#define` pour une macro avec le même nom génère un avertissement à moins que la deuxième séquence de jeton soit identique à la première.  
  
 **Section spécifique à Microsoft**  
  
 Microsoft C\/C\+\+ vous permet de redéfinir une macro si la nouvelle définition est syntaxiquement identique à la définition d'origine.  En d'autres termes, les deux définitions peuvent avoir des noms de paramètres différents.  Ce comportement diffère de [!INCLUDE[vcpransi](../preprocessor/includes/vcpransi_md.md)] C, qui requiert que les deux définitions soient lexicalement identiques.  
  
 Par exemple, les deux macros suivantes sont identiques, sauf pour les noms de paramètres.  [!INCLUDE[vcpransi](../preprocessor/includes/vcpransi_md.md)] C ne permet pas de redéfinition, mais Microsoft C\/C\+\+ le compile sans erreur.  
  
```  
#define multiply( f1, f2 ) ( f1 * f2 )  
#define multiply( a1, a2 ) ( a1 * a2 )  
```  
  
 En revanche, les deux macros suivantes ne sont pas identiques et généreront un avertissement dans Microsoft C\/C\+\+.  
  
```  
#define multiply( f1, f2 ) ( f1 * f2 )  
#define multiply( a1, a2 ) ( b1 * b2 )  
```  
  
 **FIN de la section spécifique à Microsoft**  
  
 Cet exemple illustre la directive `#define` :  
  
```  
#define WIDTH       80  
#define LENGTH      ( WIDTH + 10 )  
```  
  
 La première instruction définit l'identificateur `WIDTH` en tant que constante entière 80, puis définit `LENGTH` en tant que `WIDTH` et la constante entière 10.  Chaque occurrence de `LENGTH` est remplacée par \(`WIDTH + 10`\).  Ensuite, chaque occurrence de `WIDTH + 10` est remplacée par l'expression \(`80 + 10`\).  Les parenthèses autour de `WIDTH + 10` sont importantes car elles contrôlent l'interprétation d'instructions telles que :  
  
```  
var = LENGTH * 20;  
```  
  
 Après l'étape de prétraitement, l'instruction devient :  
  
```  
var = ( 80 + 10 ) * 20;  
```  
  
 ce qui correspond à 1800.  Sans parenthèses, le résultat est :  
  
```  
var = 80 + 10 * 20;  
```  
  
 ce qui correspond à 280.  
  
 **Section spécifique à Microsoft**  
  
 La définition des macros et des constantes avec l'option du compilateur [\/D](../build/reference/d-preprocessor-definitions.md) a le même effet que d'utiliser une directive de prétraitement `#define` au début de votre fichier.  Jusqu'à 30 macros peuvent être définies avec l'option \/D.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Directives de préprocesseur](../preprocessor/preprocessor-directives.md)