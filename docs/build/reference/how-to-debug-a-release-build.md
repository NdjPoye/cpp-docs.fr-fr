---
title: "Comment&#160;: d&#233;boguer une version release | Microsoft Docs"
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
  - "déboguer (C++), versions release"
  - "versions release, débogage"
ms.assetid: d333e4d1-4e6c-4384-84a9-cb549702da25
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Comment&#160;: d&#233;boguer une version release
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vous pouvez déboguer une version Release d'une application.  
  
### Pour déboguer une version Release  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le nœud **C\/C\+\+**.  Affectez à **Format des informations de débogage** la valeur [Compatible C7 \(\/Z7\)](../../build/reference/z7-zi-zi-debug-information-format.md) ou **Base de données du programme \(\/Zi\)**.  
  
3.  Développez **Éditeur de liens** et cliquez sur le nœud **Général**.  Attribuez à **Activation des liens incrémentiels** la valeur [Non \(\/INCREMENTAL:NO\)](../../build/reference/incremental-link-incrementally.md).  
  
4.  Sélectionnez le nœud **Débogage**.  Attribuez à **Générer des infos de débogage** la valeur [Oui \(\/DEBUG\)](../../build/reference/debug-generate-debug-info.md).  
  
5.  Sélectionnez le nœud **Optimisation**.  Attribuez à **Références** la valeur [\/OPT:REF](../../build/reference/opt-optimizations.md) et à **Activation du repli COMDAT** la valeur [\/OPT:ICF](../../build/reference/opt-optimizations.md).  
  
6.  Vous pouvez à présent déboguer l'application de version release.  Pour rechercher un problème, parcourez le code \(ou utilisez le débogage juste\-à\-temps\) jusqu'à ce que vous trouviez à quel endroit se produit l'erreur, puis déterminez le code ou les paramètres incorrects.  
  
     Si une application fonctionne dans une version Debug mais pas dans une version Release, l'une des optimisations du compilateur peut présenter une erreur dans le code source.  Pour isoler le problème, désactivez les optimisations sélectionnées pour chaque fichier de code source jusqu'à ce que vous localisiez le fichier et l'optimisation à l'origine du problème. \(Pour accélérer le processus, vous pouvez diviser les fichiers en deux groupes, désactiver l'optimisation sur un groupe, puis lorsque vous recherchez un problème dans un groupe, continuer à le diviser jusqu'à ce que vous isoliez le fichier problèmatique.\)  
  
     Vous pouvez utiliser [\/RTC](../../build/reference/rtc-run-time-error-checks.md) pour tenter d'exposer des bogues de ce type dans vos versions Debug.  
  
     Pour plus d'informations, consultez [Optimisation du code](../../build/reference/optimizing-your-code.md).  
  
## Voir aussi  
 [Résolution de problèmes liés à la version release](../../build/reference/fixing-release-build-problems.md)