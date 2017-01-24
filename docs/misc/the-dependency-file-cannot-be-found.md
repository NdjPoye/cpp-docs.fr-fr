---
title: "The dependency &#39;file&#39; cannot be found | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.tasklisterror.supdepnotfound"
ms.assetid: a0e6e658-c723-40da-8275-fa212165bd7d
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# The dependency &#39;file&#39; cannot be found
Une des références de votre projet contient elle\-même une référence \(dépendance\) qui n'a pas pu être localisée.  
  
 En cas d'inscription dans un projet sous le contrôle de code source, il se peut que vous constatiez la présence de dépendances non résolues sur l'ordinateur.  Ceci est dû au fait que la propriété de chemin d'accès de référence est une propriété spécifique à l'ordinateur et qu'elle n'est pas, par conséquent, sous le contrôle de code source.  
  
### Pour corriger cette erreur  
  
1.  Localisez la référence d'assembly indiquée sur le disque et modifiez votre propriété de chemin d'accès de référence.  
  
2.  Si vous ne pouvez pas trouver le fichier d'assembly sur le disque, vous devrez peut\-être réinstaller [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] ou tous les contrôles personnalisés tiers si les dépendances de l'assembly sont introuvables sur le disque.  De même, en cas d'inscription dans un projet sous le contrôle de code source, il se peut que vous deviez installer les contrôles de tiers nécessaires à ce projet.  
  
 Cette erreur n'empêche pas la génération du projet.  Une exception TypeLoadException peut cependant survenir lors de l'exécution de l'application.  De plus, la dépendance affectée ne sera pas indiquée dans le processus Déploiement.  
  
 Vous pouvez visualiser les références du projet dans l'Explorateur de solutions, dans le nœud **References**.  
  
## Voir aussi  
 [NIB: Reference Paths Dialog Box \(Visual Basic\)](http://msdn.microsoft.com/fr-fr/8e549b39-7256-456a-8fd7-089b23facf9c)