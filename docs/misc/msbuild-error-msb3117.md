---
title: "MSBuild Error MSB3117 | Microsoft Docs"
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
  - "MSBuild.GenerateManifest.HostInBrowserInvalidFrameworkVersion"
helpviewer_keywords: 
  - "MSB3117"
ms.assetid: 18aec642-6000-4626-bf75-f3547769c780
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3117
**MSB3117: L'application est configurée pour être hébergée dans le navigateur mais TargetFrameworkVersion a la valeur v2.0.**  
  
 Une application de navigateur Web WPF a été déployée avec la propriété <xref:Microsoft.Build.Tasks.Deployment.ManifestUtilities.ApplicationManifest.HostInBrowser%2A> mise à la valeur `True`, mais TargetFrameworkVersion a la valeur `v2.0` ou `v3.0`.  Si vous utilisez ce paramétrage, vous devez également affecter la valeur `v3.5` ou supérieure à la propriété <xref:Microsoft.Build.Tasks.GenerateApplicationManifest.TargetFrameworkVersion%2A>.  
  
### Pour corriger cette erreur  
  
-   Affectez la valeur `v3.5` ou supérieure à la propriété <xref:Microsoft.Build.Tasks.GenerateApplicationManifest.TargetFrameworkVersion%2A>.  
  
## Voir aussi  
 <xref:Microsoft.Build.Tasks.Deployment.ManifestUtilities.ApplicationManifest.HostInBrowser%2A>   
 <xref:Microsoft.Build.Tasks.GenerateApplicationManifest.TargetFrameworkVersion%2A>   
 [Page Publier, Concepteur de projets](../Topic/Publish%20Page,%20Project%20Designer.md)   
 [MSBuild Error MSB3116](../misc/msbuild-error-msb3116.md)   
 [MSBuild Error MSB3118](../misc/msbuild-error-msb3118.md)   
 [MSBuild Error MSB3174](../misc/msbuild-error-msb3174.md)   
 [MSBuild Error MSB3185](../misc/msbuild-error-msb3185.md)