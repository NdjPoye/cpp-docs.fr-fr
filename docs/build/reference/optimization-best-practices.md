---
title: "Meilleures pratiques pour l’optimisation | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Visual C++, optimisation"
  - "optimisation, meilleures pratiques"
ms.assetid: f3433148-7255-4ca6-8a4f-7c31aac88508
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Meilleures pratiques pour l’optimisation
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ce document décrit certaines des meilleures pratiques pour l'optimisation dans Visual C\+\+.  Les sujets abordés sont les suivants :  
  
-   Options du compilateur et de l'éditeur de liens  
  
    -   Optimisation guidée par profil  
  
    -   Quel niveau d'optimisation dois\-je utiliser ?  
  
    -   Commutateurs à virgule flottante  
  
-   Optimisation des declspecs  
  
-   Optimisation des pragmas  
  
-   \_\_restrict et \_\_assume  
  
-   Prise en charge intrinsèque  
  
-   Exceptions  
  
## Options du compilateur et de l'éditeur de liens  
  
### Optimisation guidée par profil  
 Visual C\+\+ prend en charge l'optimisation guidée par profil \(PGO\).  Cette optimisation utilise les données de profil des exécutions antérieures d'une version instrumentée d'une application pour exécuter une optimisation ultérieure de l'application.  Étant donné que l'optimisation PGO peut prendre du temps, elle n'est pas très utilisée par les développeurs ; toutefois, nous vous recommandons de l'utiliser pour la version release finale d'un produit.  Pour plus d'informations, consultez [Optimisations guidées par profil](../../build/reference/profile-guided-optimizations.md).  
  
 En outre, l'optimisation de l'ensemble du programme \(également appelée Génération de code durant l'édition de liens\) et les optimisations **\/O1** et **\/O2** ont été améliorées.  En général, une application compilée avec l'une de ces options s'exécute plus rapidement que la même application compilée avec un compilateur antérieur.  
  
 Pour plus d’informations, consultez [\/GL \(Optimisation de l'ensemble du programme\)](../../build/reference/gl-whole-program-optimization.md) et [\/O1, \/O2 \(Réduire la taille, augmenter la vitesse\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md).  
  
### Quel niveau d'optimisation dois\-je utiliser ?  
 Si possible, les versions release finales doivent être compilées avec les optimisations guidées par profil.  Si la génération avec l'optimisation PGO n'est pas possible, en raison d'une infrastructure insuffisante pour exécuter les versions instrumentées ou d'un accès non autorisé aux scénarios, nous vous suggérons d'exécuter la génération avec l'optimisation de l'ensemble du programme.  
  
 Le commutateur **\/Gy** est également très utile.  Il génère un COMDAT distinct pour chaque fonction, en offrant plus de flexibilité à l'éditeur de liens pour supprimer les COMDAT non référencés et le repli COMDAT.  L'utilisation de **\/Gy** présente un seul inconvénient : il peut produire un effet mineur au moment de la génération.  Par conséquent, il est généralement recommandé de l'utiliser.  Pour plus d'informations, consultez [\/Gy \(Activer la liaison au niveau des fonctions\)](../../build/reference/gy-enable-function-level-linking.md).  
  
 Pour la liaison dans les environnements 64 bits, il est recommandé d'utiliser l'option de l'éditeur de liens **\/OPT:REF,ICF**, et dans les environnements 32 bits, **\/OPT:REF** est conseillé.  Pour plus d'informations, consultez [\/OPT \(Optimisations\)](../../build/reference/opt-optimizations.md).  
  
 Il est également vivement recommandé de générer des symboles de débogage, même avec les versions release optimisées.  Cela n'affecte pas le code généré, et simplifie considérablement le débogage de votre application, si besoin est.  
  
### Commutateurs à virgule flottante  
 L'option de compilateur **\/Op** a été supprimée et les quatre options de compilateur ci\-après qui utilisent les optimisations à virgule flottante ont été ajoutées :  
  
|||  
|-|-|  
|**\/fp:precise**|Recommandation par défaut qui doit être utilisée dans la plupart des cas.|  
|**\/fp:fast**|Recommandé si les performances ont une importance majeure, par exemple dans les jeux.  On obtient des performances plus rapides.|  
|**\/fp:strict**|Recommandé si des exceptions de virgule flottante précises et un comportement IEEE sont souhaités.  On obtient des performances plus lentes.|  
|**\/fp:except\[\-\]**|Peut être utilisé conjointement avec **\/fp:strict** ou **\/fp:precise**, mais pas **\/fp:fast**.|  
  
 Pour plus d'informations, consultez [\/fp \(Spécifier le comportement de virgule flottante\)](../../build/reference/fp-specify-floating-point-behavior.md).  
  
## Optimisation des declspecs  
 Cette section présente deux declspecs qui peuvent être utilisés dans les programmes pour améliorer les performances : `__declspec(restrict)` et `__declspec(noalias)`.  
  
 Le declspec `restrict` peut être appliqué uniquement aux déclarations de fonction qui retournent un pointeur, par exemple `__declspec(restrict) void *malloc(size_t size);`  
  
 Le declspec `restrict` est utilisé sur les fonctions qui retournent des pointeurs sans alias.  Ce mot clé est utilisé pour l'implémentation de la bibliothèque runtime C de `malloc` puisqu'il ne retourne jamais une valeur de pointeur déjà utilisée dans le programme en cours \(sauf si vous effectuez une opération non autorisée, par exemple l'utilisation de la mémoire après sa libération\).  
  
 Le declspec `restrict` fournit plus d'informations au compilateur pour exécuter des optimisations de compilateur.  La détermination des pointeurs qui définissent un alias sur d'autres pointeurs est l'une des opérations les plus difficiles pour un compilateur, et l'utilisation de ces informations aide considérablement le compilateur.  
  
 Il est important de noter qu'il s'agit d'une promesse faite au compilateur, et non une information que le compilateur vérifie.  Si votre programme utilise ce declspec `restrict` de manière inappropriée, un comportement incorrect risque de se produire.  
  
 Pour plus d'informations, consultez [restrict](../../cpp/restrict.md).  
  
 Le declspec `noalias` est également appliqué uniquement aux fonctions, et indique que la fonction est une fonction semi\-pure.  Une fonction semi\-pure est une fonction qui référence ou modifie uniquement des variables locales, des arguments et des indirections d'arguments de premier niveau.  Ce declspec est une promesse faite au compilateur, et si la fonction référence des globales ou des indirections d'arguments de pointeur de second niveau, le compilateur peut générer du code qui arrête l'application.  
  
 Pour plus d'informations, consultez [noalias](../../cpp/noalias.md).  
  
## Optimisation des pragmas  
 Plusieurs pragmas utiles permettent également d'optimiser le code.  Le premier pragma que nous allons présenter est le pragma `#pragma optimize` :  
  
```  
#pragma optimize("{opt-list}", on | off)  
```  
  
 Ce pragma vous permet de définir un niveau d'optimisation donné, fonction par fonction.  Il est idéal pour les occasions rares où votre application tombe en panne lorsqu'une fonction donnée est compilée avec l'optimisation.  Vous pouvez l'utiliser pour désactiver les optimisations d'une fonction unique :  
  
```  
#pragma optimize("", off)  
int myFunc() {...}  
#pragma optimize("", on)  
```  
  
 Pour plus d'informations, consultez [optimize](../../preprocessor/optimize.md).  
  
 La fonctionnalité inline est l'une des optimisations les plus importantes exécutées par le compilateur. Nous allons présenter deux pragmas qui permettent de modifier ce comportement.  
  
 `#pragma inline_recursion` est utile pour spécifier si vous souhaitez ou non que l'application traite en mode inline un appel récurrent.  Il est désactivé par défaut.  Vous pouvez l'activer pour la récursivité superficielle de petites fonctions.  Pour plus d'informations, consultez [inline\_recursion](../../preprocessor/inline-recursion.md).  
  
 Un autre pragma utile pour limiter la profondeur de la fonctionnalité inline est `#pragma inline_depth`.  Il est généralement utile dans les situations où vous essayez de réduire la taille d'un programme ou d'une fonction.  Pour plus d'informations, consultez [inline\_depth](../../preprocessor/inline-depth.md).  
  
## \_\_restrict et \_\_assume  
 Deux mots clés dans Visual C\+\+ permettent d'améliorer les performances : [\_\_restrict](../../cpp/extension-restrict.md) et [\_\_assume](../../intrinsics/assume.md).  
  
 Tout d'abord, il faut noter que `__restrict` et `__declspec(restrict)` sont deux éléments distincts.  Même s'ils sont similaires, leur sémantique est différente.  `__restrict` est un qualificateur de type, tel que `const` ou `volatile`, mais exclusivement pour les types pointeur.  
  
 Un pointeur modifié avec `__restrict` est appelé un *pointeur \_\_restrict*.  Un pointeur \_\_restrict est un pointeur qui est uniquement accessible par le biais du pointeur \_\_restrict.  En d'autres termes, un autre pointeur ne peut pas être utilisé pour accéder aux données pointées par le pointeur \_\_restrict.  
  
 `__restrict` peut être un outil performant pour l'optimiseur Visual C\+\+, mais vous devez l'utiliser avec précaution.  S'il est utilisé de manière incorrecte, l'optimiseur peut exécuter une optimisation qui arrête votre application.  
  
 Le mot clé `__restrict` remplace le commutateur **\/Oa** des versions antérieures.  
  
 Avec `__assume,`, un développeur peut demander au compilateur de faire des hypothèses sur la valeur d'une variable.  
  
 Par exemple, `__assume(a < 5);` dit à l'optimiseur que sur cette ligne de code, la variable `a` est inférieure à 5.  Il s'agit encore d'une promesse au compilateur.  Si en réalité `a` a une valeur de 6 à ce stade du programme, le comportement du programme après l'optimisation du compilateur peut ne pas être celui que vous attendez.  `__assume` est très utile avant les instructions switch et\/ou expressions conditionnelles.  
  
 Des restrictions sont appliquées à `__assume`.  Tout d'abord, à l'instar de `__restrict`, il s'agit uniquement d'une suggestion ; le compilateur peut l'ignorer.  De même, `__assume` ne fonctionne actuellement qu'avec les inégalités variables par rapport aux constantes.  Il ne propage pas des inégalités symboliques, par exemple, assume\(a\< b\).  
  
## Prise en charge intrinsèque  
 Les éléments intrinsèques sont des appels de fonction où le compilateur a une connaissance intrinsèque sur l'appel et émet un code pour cette fonction au lieu d'appeler une fonction dans une bibliothèque.  Le fichier d'en\-tête intrin.h présent dans \<Installation\_Directory\>\\VC\\include\\intrin.h contient tous les éléments intrinsèques disponibles pour chacune des trois plateformes prises en charge \(x86, x64 et ARM\).  
  
 Les éléments intrinsèques permettent au programmeur de sonder le code sans utiliser l'assembly.  L'utilisation des éléments intrinsèques présente plusieurs avantages :  
  
1.  Votre code est plus portable.  Plusieurs des éléments intrinsèques sont disponibles sur plusieurs architectures d'UC.  
  
2.  Votre code est plus facile à lire, car il est toujours écrit dans C\/C\+\+.  
  
3.  Votre code tire profit des optimisations du compilateur.  Comme le compilateur se porte mieux, la génération du code pour les éléments intrinsèques est améliorée.  
  
 Pour plus d’informations, consultez [compilateur, intrinsèques](../../intrinsics/compiler-intrinsics.md) et [Benefits of Using Intrinsics](http://msdn.microsoft.com/fr-fr/57af8920-527f-44af-a741-a07cbe80bf02).  
  
## Exceptions  
 L'utilisation des exceptions provoque une altération des performances.  Des restrictions sont appliquées lors de l'utilisation de blocs try qui interdisent au compilateur d'exécuter certaines optimisations.  Sur les plateformes x86, on constate une altération supplémentaire des performances des blocs try en raison d'informations d'état supplémentaires qui doivent être générées pendant l'exécution du code.  Sur les plateformes 64 bits, les blocs try n'altèrent pas autant les performances, mais lorsqu'une exception est levée, le processus de recherche du gestionnaire et de déroulement de la pile peut s'avérer coûteux.  
  
 Par conséquent, il est recommandé de ne pas utiliser de blocs try\/catch dans le code qui ne sont pas vraiment utiles.  Si vous devez utiliser des exceptions, utilisez si possible des exceptions synchrones.  Pour plus d'informations, consultez [Gestion structurée des exceptions](../../cpp/structured-exception-handling-c-cpp.md).  
  
 Enfin, levez des exceptions uniquement dans des cas exceptionnels.  L'utilisation des exceptions pour le flux de contrôle général risque de provoquer une altération des performances.  
  
## Voir aussi  
 [Optimisation du code](../../build/reference/optimizing-your-code.md)