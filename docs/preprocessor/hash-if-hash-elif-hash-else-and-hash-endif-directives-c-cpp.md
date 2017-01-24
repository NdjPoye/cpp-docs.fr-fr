---
title: "Directives #if, #elif, #else et #endif (C/C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "#else"
  - "#endif"
  - "#if"
  - "#elif"
  - "Defined"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#elif (directive)"
  - "#else (directive)"
  - "#endif (directive)"
  - "#if (directive)"
  - "compilation conditionnelle, directives"
  - "defined (directive)"
  - "directive elif (#elif)"
  - "directive #else"
  - "directive endif (#endif)"
  - "directive if (#if)"
  - "préprocesseur, directives"
ms.assetid: c77a175f-6ca8-47d4-8df9-7bac5943d01b
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Directives #if, #elif, #else et #endif (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La directive `#if`, ainsi que les directives `#elif`, `#else` et `#endif`, permettent de contrôler la compilation de certaines parties d'un fichier source.  Si l'expression que vous écrivez \(après `#if`\) a une valeur différente de zéro, le groupe de lignes qui suit immédiatement la directive `#if` est conservé dans l'unité de traduction.  
  
## Grammaire  
 *conditional*  :  
 *if\-part elif\-parts* opt *else\-part*opt *endif\-line*  
  
 *if\-part*  :  
 *if\-line text*  
  
 *if\-line*  :  
 **\#if**  *constant\-expression*  
  
 **\#ifdef**  *identifier*  
  
 **\#ifndef**  *identifier*  
  
 *elif\-parts*  :  
 *elif\-line text*  
  
 *elif\-parts elif\-line text*  
  
 *elif\-line*  :  
 **\#elif**  *constant\-expression*  
  
 *else\-part*  :  
 *else\-line text*  
  
 *else\-line*  :  
 `#else`  
  
 *endif\-line*  :  
 `#endif`  
  
 Chaque directive `#if` se trouvant dans un fichier source doit correspondre à une directive `#endif` de fermeture.  N'importe quel nombre de directives `#elif` peut apparaître entre les directives `#if` et `#endif`, mais au plus une directive `#else` est autorisée.  La directive `#else`, le cas échéant, doit être la dernière directive avant `#endif`.  
  
 Les directives `#if`, `#elif`, `#else` et `#endif` peuvent s'imbriquer dans les parties de texte d'autres directives `#if`.  Chaque directive `#else`, `#elif` ou `#endif` imbriquée appartient à la directive `#if` précédente la plus proche.  
  
 Toutes les directives de compilation conditionnelle, telles que `#if` et **\#ifdef**, doivent correspondre à des directives `#endif` de fermeture avant la fin du fichier ; sinon, un message d'erreur est généré.  Lorsque les directives de compilation conditionnelle sont contenues dans les fichiers Include, elles doivent satisfaire aux mêmes conditions : il ne doit y avoir aucune directive de compilation conditionnelle sans correspondance à la fin du fichier Include.  
  
 Le remplacement de macro est effectué dans la partie de la ligne de commande qui suit une commande `#elif`. Par conséquent, un appel de macro peut être utilisé dans *constant\-expression*.  
  
 Le préprocesseur sélectionne l'une des occurrences données de *text* en vue d'un traitement ultérieur.  Un bloc spécifié dans *text* peut être n'importe quelle séquence de texte.  Il peut occuper plusieurs lignes.  Généralement, l'élément *text* est un texte de programme qui a une signification pour le compilateur ou le préprocesseur.  
  
 Le préprocesseur traite l'élément *text* sélectionné et le transmet au compilateur.  Si l'élément *text* contient des directives de préprocesseur, le préprocesseur exécute ces directives.  Seuls les blocs de texte sélectionnés par le préprocesseur sont compilés.  
  
 Le préprocesseur sélectionne un seul élément *text* en évaluant l'expression constante qui suit chaque directive `#if` ou `#elif` jusqu'à ce qu'il trouve une expression constante vraie \(différente de zéro\).  Il sélectionne tout le texte \(y compris les autres directives de préprocesseur avec **\#**\) jusqu'à la directive `#elif`, `#else` ou `#endif` qui lui est associée.  
  
 Si toutes les occurrences de *constant\-expression* ont la valeur false ou qu'aucune directive `#elif` n'apparaît, le préprocesseur sélectionne le bloc de texte après la clause `#else`.  Si la clause `#else` est omise et que toutes les instances de l'élément *constant\-expression* dans le bloc `#if` ont la valeur false, aucun bloc de texte n'est sélectionné.  
  
 L'élément *constant\-expression* est une expression constante entière avec les restrictions supplémentaires suivantes :  
  
-   Les expressions doivent être de type intégral et ne peuvent inclure que des constantes entières, des constantes caractère et l'opérateur **defined**.  
  
-   L'expression ne peut pas utiliser `sizeof` ou un opérateur de cast de type.  
  
-   Il se peut que l'environnement cible ne puisse pas représenter toutes les plages d'entiers.  
  
-   La traduction représente le type `int` de la même manière que le type **long**, et le type `unsigned int` de la même manière que le type `unsigned long`.  
  
-   Le traducteur peut traduire les constantes caractère en un ensemble de valeurs de code différentes de l'ensemble de l'environnement cible.  Pour déterminer les propriétés de l'environnement cible, vérifiez les valeurs des macros de LIMITS.H dans une application développée pour l'environnement cible.  
  
-   L'expression ne doit effectuer aucune interrogation de l'environnement et doit rester isolée par rapport aux détails d'implémentation sur l'ordinateur cible.  
  
 L'opérateur de préprocesseur **defined** peut être utilisé dans les expressions constantes spéciales, comme indiqué par la syntaxe suivante :  
  
 defined\( `identifier` \)  
  
 defined `identifier`  
  
 Cette expression constante est considérée comme True \(différente de zéro\) si *identifier* est actuellement défini ; sinon, la condition a la valeur False \(0\).  Un identificateur défini comme du texte vide est considéré comme défini.  La directive **defined** peut être utilisée dans une directive `#if` et une directive `#elif`, mais nulle part ailleurs.  
  
 Dans l'exemple suivant, les directives `#if` et `#endif` contrôlent la compilation de l'un des trois appels de fonction suivants :  
  
```  
#if defined(CREDIT)  
    credit();  
#elif defined(DEBIT)  
    debit();  
#else  
    printerror();  
#endif  
```  
  
 L'appel de fonction à `credit` est compilé si l'identificateur `CREDIT` est défini.  Si l'identificateur `DEBIT` est défini, l'appel de fonction à `debit` est compilé.  Si aucun de ces deux identificateurs n'est défini, l'appel de `printerror` est compilé.  Notez que `CREDIT` et `credit` sont des identificateurs distincts en C et C\+\+, car leurs casses sont différentes.  
  
 Les instructions de compilation conditionnelle dans l'exemple suivant supposent une constante symbolique définie au préalable et nommée `DLEVEL`.  
  
```  
#if DLEVEL > 5  
    #define SIGNAL  1  
    #if STACKUSE == 1  
        #define STACK   200  
    #else  
        #define STACK   100  
    #endif  
#else  
    #define SIGNAL  0  
    #if STACKUSE == 1  
        #define STACK   100  
    #else  
        #define STACK   50  
    #endif  
#endif  
#if DLEVEL == 0  
    #define STACK 0  
#elif DLEVEL == 1  
    #define STACK 100  
#elif DLEVEL > 5  
    display( debugptr );  
#else  
    #define STACK 200  
#endif  
```  
  
 Le premier bloc `#if` montre deux ensembles de directives `#if`, `#else` et `#endif` imbriquées.  Le premier jeu de directives est traité uniquement si `DLEVEL > 5` a la valeur true.  Sinon, les instructions situées après \#**else** sont traitées.  
  
 Les directives `#elif` et `#else` dans le deuxième exemple sont utilisées pour effectuer l'un des quatre choix possibles, selon la valeur de `DLEVEL`.  La constante `STACK` a la valeur 0, 100 ou 200, selon la définition de `DLEVEL`.  Si `DLEVEL` est supérieur à 5, l'instruction  
  
```  
#elif DLEVEL > 5  
display(debugptr);  
```  
  
 est compilée et `STACK` n'est pas défini.  
  
 Une utilisation courante de la compilation conditionnelle consiste à empêcher plusieurs inclusions du même fichier d'en\-tête.  En C\+\+, où les classes sont souvent définies dans des fichiers d'en\-tête, des constructions telles que les suivantes peuvent être utilisées pour empêcher plusieurs définitions :  
  
```  
/*  EXAMPLE.H - Example header file  */  
#if !defined( EXAMPLE_H )  
#define EXAMPLE_H  
  
class Example  
{  
...  
};  
  
#endif // !defined( EXAMPLE_H )  
```  
  
 Le code précédent vérifie si la constante symbolique `EXAMPLE_H` est définie.  Si oui, le fichier a déjà été inclus et il est inutile de le retraiter.  Sinon, la constante `EXAMPLE_H` est définie pour marquer EXAMPLE.H comme déjà traité.  
  
## Voir aussi  
 [Directives de préprocesseur](../preprocessor/preprocessor-directives.md)