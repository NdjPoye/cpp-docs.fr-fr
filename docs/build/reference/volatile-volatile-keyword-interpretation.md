---
title: "/volatile (interpr&#233;tation de mot cl&#233; volatile) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/volatile:iso"
  - "/volatile:ms"
  - "/volatile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/volatile (option du compilateur)"
  - "/volatile (option du compilateur) [C++]"
  - "volatile (option du compilateur)"
  - "-volatile (option du compilateur)"
  - "volatile (option du compilateur) [C++]"
  - "volatile (option du compilateur) [C++]"
ms.assetid: 9d08fcc6-5bda-44c8-8151-8d8d54f164b8
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# /volatile (interpr&#233;tation de mot cl&#233; volatile)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie la façon dont le mot clé [volatile](../../cpp/volatile-cpp.md) doit être interprété.  
  
## Syntaxe  
  
```  
/volatile:{iso|ms}  
```  
  
## Arguments  
 **\/volatile:iso**  
 Sélectionne une sémantique `volatile` stricte, telle qu'elle est définie par le langage C\+\+ de la norme ISO.  Les sémantiques d'acquisition\/libération ne sont pas garanties sur les accès volatiles.  Si le compilateur cible ARM, il s'agit de l'interprétation par défaut de `volatile`.  
  
 **\/volatile:ms**  
 Sélectionne une sémantique `volatile` étendue Microsoft, qui ajoute des garanties en matière d'ordonnancement en mémoire, par rapport au langage C\+\+ de la norme ISO.  Les sémantiques d'acquisition\/libération sont garanties sur les accès volatiles.  Toutefois, cette option force également le compilateur à générer des barrières de mémoire matérielle, ce qui peut ajouter une charge mémoire significative sur ARM et d'autres architectures d'ordonnancement de mémoire faibles.  Si le compilateur cible une plateforme autre qu'ARM, il 'agit d'une interprétation par défaut de `volatile`.  
  
## Notes  
 Nous vous recommandons fortement d'utiliser **\/volatile:iso** avec les primitives explicites de synchronisation et les intrinsèques du compilateur lorsque vous utilisez la mémoire partagée par les threads.  Pour plus d'informations, consultez [volatile](../../cpp/volatile-cpp.md).  
  
 Si vous déplacez le code existant ou modifiez cette option au milieu d'un projet, il peut être utile d'activer l'avertissement [C4746](../../error-messages/compiler-warnings/compiler-warning-c4746.md) pour identifier les emplacements de code affectés par la différence de sémantique.  
  
 Il n'existe aucun `#pragma` équivalent pour contrôler cette option.  
  
### Pour définir l'option du compilateur \/volatile dans Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Sélectionnez le dossier **C\/C\+\+**.  
  
3.  Sélectionnez la page de propriétés **Ligne de commande**.  
  
4.  Dans la zone **Options supplémentaires**, ajoutez `/volatile:iso` ou `/volatile:ms`.  
  
## Voir aussi  
 [volatile](../../cpp/volatile-cpp.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)