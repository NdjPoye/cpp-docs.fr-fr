---
title: "Probl&#232;mes courants de migration ARM Visual&#160;C++ | Microsoft Docs"
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
ms.assetid: 0f4c434e-0679-4331-ba0a-cc15dd435a46
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Probl&#232;mes courants de migration ARM Visual&#160;C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Même code source Visual C\+\+ peut produire des résultats différents sur l'architecture de ARM qu'il effectue sur x86 ou x64 les architectures.  
  
## Sources de problèmes de migration  
 De nombreux problèmes que vous pouvez rencontrer lorsque vous effectuez le code de les architectures x86 ou x64 à l'architecture de ARM sont liés aux éléments de code source qui peuvent appeler non défini, l'implémentation définis, ou comportement non spécifié.  
  
 Comportement non défini  
 Comportement que la norme C\+\+ ne définit pas, et qui est provoquée par une opération qui n'a pas de sens résultat\- pour l'exemple, la conversion d'une valeur à virgule flottante en entier non signé, ou déplaçant une valeur par plusieurs positions qui est négative ou dépasse le nombre de bits dans son type de sa promotion.  
  
 Comportement implémentation défini  
 Comportement que la norme C\+\+ nécessite que le constructeur du compilateur de définir et documenter.  Un programme peut sans risque compter sur le comportement implémentation défini, bien que cela ne soit pas portable.  Les exemples du comportement implémentation défini incluent les tailles des types de données prédéfinis et leurs spécifications d'alignement.  Un exemple d'une opération qui peut être affectée par le comportement implémentation défini accède à la liste d'arguments variable.  
  
 Comportement non spécifié  
 Ce comportement les feuilles C\+\+ standard intentionnellement non déterministes.  Bien que le comportement soit considéré comme étant non déterministe, des appels spécifiques du comportement non spécifié sont déterminés par l'implémentation du compilateur.  Toutefois, il n'existe aucune exigence pour un constructeur de compilateur prédétermine le résultat ou de garantit un comportement cohérent entre les appels comparables, et il n'existe aucune exigence pour la documentation.  Un exemple du comportement non spécifié est l'ordre dans lequel Sub\-expression\- qui incluent des arguments à une fonction appel\- sont évalués.  
  
 D'autres problèmes de migration peuvent être réaffectées les différences de matériel entre ARM et x86 ou x64 les architectures qui interagissent avec la norme C\+\+ différemment.  Par exemple, le modèle de stockage forte du x86 et x64 de l'architecture fournit `volatile`\- variables qualifiées des propriétés supplémentaires utilisées pour simplifier certains genres de communication d'entre les threads dans le passé.  Mais le modèle de mémoire libre de l'architecture de ARM ne prend pas en charge cette utilisation, ni la norme C\+\+ l'exige.  
  
> [!IMPORTANT]
>  Bien qu' `volatile` gagne certaines propriétés qui peuvent être utilisées pour implémenter les formulaires limitées de communication d'entre les threads sur x86 et x64, ces propriétés supplémentaires ne sont pas suffisantes pour implémenter une communication d'entre les threads en général.  La norme C\+\+ recommandé que cette communication est implémentée à l'aide de primitives de synchronisation appropriés à la place.  
  
 Étant donné que les différentes plateformes peuvent exprimer ces types de comportement différemment, déplacer le logiciel entre les plateformes peut être difficile et bogue\- rubrique s'il dépend du comportement d'une plateforme spécifique.  Bien que plusieurs de ces types de comportement puissent être observés et peuvent sembler stable, compter sur eux est au moins non portables, et lorsqu'il s'agit du comportement non défini ou non spécifié, est également une erreur.  Le même comportement qui est mentionné dans ce document ne doit pas être compté sur, et peut changer dans les futurs compilateurs ou implémentations de l'UC.  
  
## Problèmes de migration d'exemple  
 Le reste de ce document décrit comment le comportement différent de ces éléments de langage C\+\+ peut produire des résultats différents sur des plateformes différentes.  
  
### Conversion de virgule flottante en entier non signé  
 Dans l'architecture de ARM, la conversion d'une valeur à virgule flottante à un entier 32 bits sature à la valeur la plus proche que l'entier peut représenter si la valeur à virgule flottante est en dehors de la plage à l'entier peut représenter.  Sur x86 et les architectures x64, les encapsule de conversion autour si l'entier non signé, ou est définie à \-2147483648 si l'entier signé.  Aucune de ces architectures ne prend directement la conversion des valeurs à virgule flottante à des plus petits types d'entiers ; à la place, les conversions sont exécutées à 32 bits, et les résultats sont tronqués à une petite taille.  
  
 Pour l'architecture de ARM, la combinaison de la saturation et de la troncation signifie que la conversion des types non signés sature correctement petits types non signés lorsqu'elle sature un entier 32 bits, mais produit un résultat tronqué pour les valeurs qui sont plus importants que le type plus petit peut représenter mais trop petit pour saturer l'entier 32 bits complet.  La conversion sature également correctement pour l'entier 32 bits signé, mais la troncation de saturer, entier signé entraîne \-1 pour les valeurs positif\- saturées et 0 pour les valeurs négatif\- saturées.  La conversion à un plus petit entier signé produit un résultat tronqué qui est imprévisible.  
  
 Pour x86 et les architectures x64, la combinaison du comportement enveloppant pour les conversions d'entier non signé et de l'évaluation explicite pour les conversions d'entier signé sur le dépassement de capacité, ainsi que la troncation, rendent les résultats pour la plupart des décalages imprévisibles s'ils sont trop volumineux.  
  
 Ces plateformes diffèrent également dans la manière dont ils gèrent la conversion de Non Non\-un\- \(nombre\) aux types d'entiers.  Sur ARM, convertit de Non à 0x00000000 ; sur x86 et x64, il convertit en 0x80000000.  
  
 Il peut seulement compter sur la conversion à virgule flottante si vous savez que la valeur est dans la plage du type entier qu'elle est convertie en.  
  
### Comportement d'opérateur de décalage \(\<\< \>\>\)  
 Dans l'architecture de ARM, une valeur peut être déplacée à gauche ou jusqu'à 255 bits avant que le modèle commence à répétition.  Sur x86 et les architectures x64, le modèle est répété à chaque multiple de 32 à moins que la source du modèle soit une variable 64 bits ; dans ce cas, les répétitions de modèle à chaque multiple de 64 sur x64, et chaque multiple de 256 sur x86, où une implémentation logicielle est utilisée.  Par exemple, pour une variable de 32 bits qui a la valeur 1 déplacé à gauche de 32 caractères, de ARM le résultat est 0, sur x86 le résultat est 1, et x64 sur le résultat est également 1.  Toutefois, si la source de la valeur est une variable 64 bits, le résultat sur les trois plateformes est 4294967296, et la valeur « n'enroule pas autour de » jusqu'à ce qu'il a déplacé 64 emplacements sur x64, ou 256 positions de ARM et x86.  
  
 Étant donné que le résultat d'une opération de décalage qui dépasse le nombre de bits dans le type de source n'est pas défini, le compilateur n'a pas besoin de présenter un comportement cohérent dans toutes les situations.  Par exemple, si les deux opérandes d'un décalage sont connus au moment de la compilation, le compilateur peut optimiser le programme à l'aide d'une routine interne au précalcule le résultat du décalage puis de remplacer le résultat à la place de l'opération de décalage.  Si le nombre de positions de décalage est trop important, ou négatif, le résultat de la routine interne peut être différent du résultat de la même expression de décalage qu'exécuté par le processeur.  
  
### Comportement d'arguments variable \(varargs\)  
 Dans l'architecture de ARM, les paramètres de la liste d'arguments variable qui sont passés de la pile sont soumis aux alignement.  Par exemple, un paramètre 64 bits est aligné sur une limite 64 bits.  Sur x86 et x64, les arguments passés dans la pile ne sont pas soumis aux alignement et pack n'est pas fortement.  Cette différence peut faire lire une fonction variadic comme `printf` les adresses mémoire qui ont été conçues comme remplissage sur ARM si la disposition souhaitée dans la liste d'arguments variable n'est pas une correspondance exacte, bien qu'elle fonctionne pour un sous\-ensemble de certaines valeurs sur x86 ou x64 les architectures.  Considérez cet exemple :  
  
```  
// notice that a 64-bit integer is passed to the function, but '%d' is used to read it.  
// on x86 and x64 this may work for small values because %d will “parse” the low-32 bits of the argument.  
// on ARM the calling convention will align the 64-bit value and the code will print a random value  
printf("%d\n", 1LL);  
  
```  
  
 Dans ce cas, un bogue peut être résolu en s'assurant que la spécification de format correcte est utilisée afin que l'alignement de l'argument est considérée comme.  Ce code est correct :  
  
```  
// CORRECT: use %I64d for 64-bit integers  
printf("%I64d\n", 1LL);  
  
```  
  
### Ordre d'évaluation d'argument  
 Étant donné que ARM, x86, et les processeurs x64 sont si différents, ils peuvent présenter des spécifications aux implémentations de compilateur, et également différentes possibilités pour les optimisations.  De ce fait, ainsi que d'autres facteurs souhaitez les paramètres de convention d'appel et d'optimisation, un compilateur peut évaluer les arguments de fonction dans un ordre différent sur différentes architectures ou lorsque les autres facteurs sont modifiés.  Cela peut provoquer un comportement d'une application qui repose sur un ordre spécifique d'évaluation de modifier de façon inattendue.  
  
 Ce type d'erreur peut se produire lorsque les arguments à une fonction avoir des effets secondaires qui effectuent d'autres arguments à la fonction dans le même appel.  Généralement il est facile d'éviter ce type de dépendance, mais il peut parfois être masqué par les dépendances il est difficile discerner que, ou par la surcharge d'opérateur.  Considérez cet exemple de code :  
  
```  
handle memory_handle;  
  
memory_handle->acquire(*p);  
  
```  
  
 Cela est bien défini, mais si `->` et `*` sont les opérateurs surchargés, ce code est traduit dans une chaîne qui ressemble à ceci :  
  
```  
Handle::acquire(operator->(memory_handle), operator*(p));  
```  
  
 Et s'il y a une dépendance entre `operator->(memory_handle)` et `operator*(p)`, le code peut dépendre un ordre spécifique d'évaluation, même si le code d'origine ressemble à il ne soit pas de dépendances possible.  
  
### comportement par défaut du mot clé volatile  
 Le compilateur Microsoft C\+\+ prend en charge deux traductions différentes du qualificateur de mémoire volatile que vous pouvez spécifier à l'aide de les commutateurs de compilation.  Le commutateur d' **\/volatile:ms** sélectionne la sémantique volatile étendue par Microsoft qui vérifient le classement fort, comme a été le point de droite traditionnel pour x86 et x64 sur le compilateur Microsoft en raison de le modèle de stockage forte sur les architectures.  Le commutateur d' **\/volatile:iso** sélectionne la sémantique de type stricte volatile standard C\+\+ qui ne vérifient pas classer fort.  
  
 Dans l'architecture de ARM, la valeur par défaut est **\/volatile:iso** car les processeurs de ARM ont un modèle de stockage faiblement dimensionné, et que le logiciel de ARM n'a pas d'héritage de compter sur la sémantique étendue d' **\/volatile:ms** et ne doit pas généralement interagir au logiciel qui fait.  Toutefois, il est toujours parfois utile ou même requis pour compiler un programme d'armement pour utiliser la sémantique étendue.  Par exemple, il peut être trop coûteux pour déplacer un programme pour utiliser la sémantique ISO C\+\+, ou le logiciel de pilote peut avoir à adhérer à la sémantique traditionnelle pour fonctionner correctement.  Dans ces cas, vous pouvez utiliser le commutateur d' **\/volatile:ms** ; toutefois, pour recréer la sémantique volatile traditionnelle sur les cibles de ARM, le compilateur doit insérer des barrières de mémoire autour de chaque lus ou de l'écriture d'une variable d' `volatile` pour appliquer le classement fort, qui peut avoir un impact négatif sur les performances.  
  
 Sur x86 et les architectures x64, la valeur par défaut est **\/volatile:ms** car une grande partie du logiciel qui a été créé pour les architectures à l'aide de le compilateur Microsoft C\+\+ repose sur elles.  Lorsque vous compilez x86 et x64 les programmes, vous pouvez spécifier le commutateur d' **\/volatile:iso** pour éviter la confiance inutile sur la sémantique volatile traditionnelle, et à favoriser la portabilité.  
  
## Voir aussi  
 [Configuration des programmes pour les processeurs ARM](../build/configuring-programs-for-arm-processors-visual-cpp.md)