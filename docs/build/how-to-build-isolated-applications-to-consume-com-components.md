---
title: "Comment&#160;: g&#233;n&#233;rer des applications isol&#233;es pour consommer des composants COM | Microsoft Docs"
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
  - "applications isolées (C++)"
ms.assetid: 04587547-1174-44ab-bd99-1292358fba20
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Comment&#160;: g&#233;n&#233;rer des applications isol&#233;es pour consommer des composants COM
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les applications isolées sont des applications qui ont des manifestes intégrés au programme.  Vous pouvez créer des applications isolées pour consommer des composants COM.  
  
### Pour ajouter des références COM aux manifestes d'applications isolées  
  
1.  Ouvrez les pages de propriétés de projet de l'application isolée.  
  
2.  Développez le nœud **Propriétés de configuration**, puis développez le nœud **Outil Manifeste**.  
  
3.  Sélectionnez la page de propriétés **COM isolé**, et puis définissez la propriété **Nom de fichier du composant** avec le nom du composant COM que vous souhaitez que l'application isolée consomme.  
  
4.  Cliquez sur **OK**.  
  
### Pour générer des manifestes dans des applications isolées  
  
1.  Ouvrez les pages de propriétés de projet de l'application isolée.  
  
2.  Développez le nœud **Propriétés de configuration**, puis développez le nœud **Outil Manifeste**.  
  
3.  Sélectionnez la page de propriétés **Entrée et sortie**, puis définissez la propriété **Incorporer le manifeste** à **Oui**.  
  
4.  Cliquez sur **OK**.  
  
5.  Générez la solution.  
  
## Voir aussi  
 [Applications isolées](http://msdn.microsoft.com/library/aa375190)   
 [Assemblys côte à côte](_win32_side_by_side_assemblies)