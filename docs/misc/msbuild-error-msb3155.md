---
title: "MSBuild Error MSB3155 | Microsoft Docs"
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
  - "MSBuild.GenerateBootstrapper.ProductNotFound"
helpviewer_keywords: 
  - "MSB3155"
ms.assetid: 59bf2293-ef13-4bb1-8f29-5d6966bbe313
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3155
**Erreur MSBuild MSB3155 : Impossible de trouver l'élément '\<package\>' dans '\<CheminAccès\>'**  
  
 Cet avertissement se produit lorsqu'un package contenant le <xref:Microsoft.Build.Tasks.Deployment.Bootstrapper.Product.ProductCode%2A> spécifié est introuvable dans le cache du programme d'amorçage.  
  
> [!NOTE]
>  MDAC \(Microsoft Data Access Components\) n'est plus inclus comme package de programme d'amorçage.  Vous pouvez le télécharger à partir du site Web [Microsoft Windows Update](http://go.microsoft.com/fwlink/?LinkId=86676).  
  
### Pour corriger cette erreur  
  
-   Supprimez le package de la liste des packages à installer ou ajoutez le package au cache.  Assurez\-vous également que le manifeste est mis en forme correctement à l'aide de balises XML valides.  
  
## Voir aussi  
 [Référence du schéma de produit et de package](../Topic/Product%20and%20Package%20Schema%20Reference.md)   
 [\<PackageFiles\>, élément](../Topic/%3CPackageFiles%3E%20Element%20\(Bootstrapper\).md)   
 [Composants requis, boîte de dialogue](../Topic/Prerequisites%20Dialog%20Box.md)   
 [Création de packages de programme d'amorçage](../Topic/Creating%20Bootstrapper%20Packages.md)