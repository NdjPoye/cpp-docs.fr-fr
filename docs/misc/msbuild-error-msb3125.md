---
title: "MSBuild Error MSB3125 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GenerateManifest.FileAssociationsNoEntryPoint"
helpviewer_keywords: 
  - "MSB3125"
ms.assetid: f8a08b05-1946-4788-8577-ceefde785e95
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3125
**MSB3125 : L'application utilise des associations de fichiers mais n'a aucun paramètre de build EntryPoint.**  
  
 Cette erreur se produit lorsqu'aucun paramètre de build entryPoint n'est présent.  Lorsque vous configurez une application afin d'utiliser des associations de fichiers, le manifeste de l'application doit contenir un paramètre de build entryPoint.  L'élément \<entryPoint\> identifie l'assembly à exécuter lorsque l'application est exécutée.  
  
### Pour corriger cette erreur  
  
-   Affectez une valeur valide à l'élément entryPoint \(voir [\<entryPoint\> Element](../Topic/%3CentryPoint%3E%20Element%20\(ClickOnce%20Application\).md)\).  Pour plus d'informations, consultez [ClickOnce Application Manifest](../Topic/ClickOnce%20Application%20Manifest.md).  
  
## Voir aussi  
 [Page Publier, Concepteur de projets](../Topic/Publish%20Page,%20Project%20Designer.md)   
 [ClickOnce Application Manifest](../Topic/ClickOnce%20Application%20Manifest.md)