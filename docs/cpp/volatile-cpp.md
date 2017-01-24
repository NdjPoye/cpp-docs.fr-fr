---
title: "volatile (C++) | Microsoft Docs"
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
  - "volatile_cpp"
  - "volatile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gestionnaires d'interruption et mot clé volatile"
  - "objets (C++), volatile"
  - "volatile (mot clé) (C++)"
  - "objets volatiles"
ms.assetid: 81db4a85-ed5a-4a2c-9a53-5d07a771d2de
caps.latest.revision: 43
caps.handback.revision: 43
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# volatile (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un qualificateur de type que vous pouvez utiliser pour spécifier qu'un objet peut être modifié dans le programme par le matériel.  
  
## Syntaxe  
  
```  
  
volatile declarator ;  
```  
  
## Notes  
 Vous pouvez utiliser le commutateur de compilation de [\/volatile](../build/reference/volatile-volatile-keyword-interpretation.md) pour changer la manière dont le compilateur interprète ce mot clé.  
  
 Visual Studio interprète le mot clé `volatile` différemment selon l'architecture cible.  Pour ARM, si aucune option du compilateur pour **\/volatile** n'est spécifiée, le compilateur exécute comme si **\/volatile:iso** a été spécifié.  Pour les architectures autres que ARM, si aucune option du compilateur pour **\/volatile** n'est spécifiée, le compilateur exécute comme si **\/volatile:ms** avait été spécifié ; Par conséquent, pour les architectures autres que ARM nous recommandons vivement de spécifier **\/volatile:iso**, et d'utiliser des primitives et des intrinsèques du compilateur explicites de synchronisation lorsque vous utilisez la mémoire partagée par les threads.  
  
 Vous pouvez utiliser le qualificateur `volatile` pour fournir l'accès aux emplacements de mémoire utilisés par des processus asynchrones tels que les gestionnaires d'interruptions.  
  
 Lorsque `volatile` est utilisé dans une variable qui détient le mot clé [\_\_restrict](../cpp/extension-restrict.md), `volatile` a la priorité.  
  
 Si un membre de `struct` est marqué comme `volatile`, `volatile` est propagé à la structure entière.  Si une structure n'a pas une longueur qui peut être copiée sur l'architecture actuelle en utilisant une instruction, `volatile` peut être complètement perdu sur cette structure.  
  
 Le mot clé `volatile` peut n'avoir aucun effet sur un champ si l'une des conditions suivantes est vraie :  
  
-   Longueur du champ volatile dépasse la taille maximale pouvant être copiée sur l'architecture actuelle en utilisant une instruction.  
  
-   La longueur du contenant extérieur `struct`—ou s'il est membre de `struct`probablement imbriqué — dépasse la taille maximale pouvant être copiée sur l'architecture actuelle en utilisant une instruction.  
  
 Bien que le processeur ne réorganise pas de nouveau les accès mémoire non\-cache, les variables non\-cache doivent être marquées comme `volatile` pour garantir que le compilateur ne réorganise pas les accès mémoire.  
  
 Objets déclarés comme `volatile` ne sont pas utilisés dans certaines optimisations car leurs valeurs peuvent changer à tout moment.  Le système affiche toujours la valeur actuelle d'un objet volatile lorsqu'il est demandé, même si une instruction précédente a demandé une valeur du même objet.  De même, la valeur de l'objet est écrite immédiatement sur l'assignation.  
  
## Conforme à l'ISO  
 Si vous êtes familier avec le mot clé [Composé volatile C\#](../Topic/volatile%20\(C%23%20Reference\).md), ou familier avec le comportement `volatile` dans les versions antérieures de Visual C\+\+, sachez que le mot clé `volatile` du standard ISO C\+\+11 est différent et est pris en charge dans Visual Studio lorsque l'option du compilateur de [\/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) est spécifiée. \(Pour ARM, c'est spécifié par défaut\).  Le mot clé `volatile` dans le code Standard C\+\+11 ISO doit être utilisé que pour l'accès matériels ; ne l'utilisez pas pour la communication entre les threads.  Pour la transmission d'entre les threads, utilisez des mécanismes d'utilisation comme [std::atomic\<T\>](../standard-library/atomic.md) de la [Standard Template Library C\+\+](../standard-library/cpp-standard-library-reference.md).  
  
## Fin ISO conforme  
  
## Spécifique à Microsoft  
 Lorsque l'option du compilateur pour **\/volatile:ms** est utilisé—par la valeur par défaut lorsque les architectures autres que ARM sont ciblées—génèrent un code supplémentaire pour maintenir la commande entre les références aux objets volatiles en plus de gérer la commande aux références à d'autres objets globaux.  En particulier :  
  
-   Une écriture à un objet volatile \(également appelée l'écriture volatile\) comporte une sémantique de version ; autrement dit, une référence à un objet global ou statique qui se produit avant qu'une écriture à un objet volatile dans la séquence d'instruction se produise avant que volatile écrive dans le fichier binaire compilé.  
  
-   Une lecture d'un objet volatile \(également appelée " volatile lu"\) a Acquérir la sémantique ; autrement dit, une référence à un objet global ou statique qui se produit après une lecture de mémoire volatile dans la séquence d'instruction se produise elle\-même après que volatile ai lu le contenu du fichier compilé.  
  
 Cela permet aux objets volatile d'être utilisé pour les verrous et des versions de mémoire dans les applications multithread.  
  
> [!NOTE]
>  Lorsqu'il repose sur la garantie améliorée fournie quand l'option du compilateur pour **\/volatile:ms** est utilisée, le code n'est pas portable.  
  
## Fin spécifique à Microsoft  
  
## Voir aussi  
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [const](../cpp/const-cpp.md)   
 [Pointeurs const et volatile](../cpp/const-and-volatile-pointers.md)