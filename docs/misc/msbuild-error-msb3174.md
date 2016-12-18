---
title: "MSBuild Error MSB3174 | Microsoft Docs"
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
  - "MSBuild.GenerateManifest.InvalidValue"
helpviewer_keywords: 
  - "MSB3174"
ms.assetid: 6f9a040c-7f21-40fd-bf74-03f99f265e79
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3174
**MSB3174 : Valeur non valide pour '\<fichier\>'.**  
  
 Cette erreur est générée lorsque le processus de génération détecte un problème général durant la vérification du format d'un fichier manifeste.  Le message d'erreur fait référence au nom du fichier manifeste.  
  
 La définition incorrecte de l'un des paramètres ci\-après générera ce message d'erreur.  Chaque paramètre répertorié est un <xref:Microsoft.Build.Tasks.GenerateApplicationManifest> ou une propriété <xref:Microsoft.Build.Tasks.GenerateDeploymentManifest> telle que <xref:Microsoft.Build.Tasks.GenerateApplicationManifest.TargetFrameworkVersion%2A> ou <xref:Microsoft.Build.Tasks.GenerateDeploymentManifest.MinimumRequiredVersion%2A>.  
  
 Lorsque la tâche est <xref:Microsoft.Build.Tasks.GenerateApplicationManifest>, les spécifications suivantes s'appliquent :  
  
|Paramètre|Configuration requise|  
|---------------|---------------------------|  
|<xref:Microsoft.Build.Tasks.GenerateManifestBase.AssemblyName%2A>|Doit être un nom de fichier valide.|  
|<xref:Microsoft.Build.Tasks.GenerateManifestBase.AssemblyVersion%2A>|Présente les mêmes spécifications que <xref:System.Version.%23ctor%2A>.  Tous les octets doivent être supérieurs à 0.  Vous devez spécifier les quatre octets.  Une chaîne vide est acceptée.|  
|<xref:Microsoft.Build.Tasks.GenerateApplicationManifest.ClrVersion%2A>|Présente les mêmes spécifications que <xref:System.Version.%23ctor%2A>.  Tous les octets doivent être supérieurs à 0.  Vous devez spécifier les quatre octets.  Une chaîne vide est acceptée.|  
|<xref:Microsoft.Build.Tasks.GenerateApplicationManifest.OSVersion%2A>|Présente les mêmes spécifications que <xref:System.Version.%23ctor%2A>.  Tous les octets doivent être supérieurs à 0.  Vous devez spécifier les quatre octets.  Une chaîne vide est acceptée.|  
|<xref:Microsoft.Build.Tasks.GenerateManifestBase.Platform%2A>|Doit être **AnyCPU**, **x86**, **x64** ou **Itanium**.  Une chaîne vide est acceptée.|  
|<xref:Microsoft.Build.Tasks.GenerateApplicationManifest.ManifestType%2A>|Doit être **Natif** ou **ClickOnce**.|  
|<xref:Microsoft.Build.Tasks.GenerateManifestBase.TargetCulture%2A>|Ce peut être une chaîne vide.  Peut également être une culture neutre \(spécifiée uniquement par le code de langue à deux lettres minuscules par exemple, "jp" pour le japonais\).  Sinon, cette valeur présente les mêmes spécifications que <xref:System.Globalization.CultureInfo.%23ctor%2A>.|  
|<xref:Microsoft.Build.Tasks.GenerateApplicationManifest.TargetFrameworkVersion%2A>|Doit avoir le format v*\#*.*\#*.  Il doit être supérieur à v2.0.  Une chaîne vide est acceptée.|  
  
 Lorsque la tâche est <xref:Microsoft.Build.Tasks.GenerateDeploymentManifest>, les spécifications suivantes s'appliquent :  
  
|Paramètre|Configuration requise|  
|---------------|---------------------------|  
|<xref:Microsoft.Build.Tasks.GenerateManifestBase.AssemblyName%2A>|Doit être un nom de fichier valide.|  
|<xref:Microsoft.Build.Tasks.GenerateManifestBase.AssemblyVersion%2A>|Présente les mêmes spécifications que <xref:System.Version.%23ctor%2A>.  Tous les octets doivent être supérieurs à 0.  Vous devez spécifier les quatre octets.  Une chaîne vide est acceptée.|  
|<xref:Microsoft.Build.Tasks.GenerateDeploymentManifest.MinimumRequiredVersion%2A>|Présente les mêmes spécifications que <xref:System.Version.%23ctor%2A>.  Tous les octets doivent être supérieurs à 0.  Une chaîne vide est acceptée.|  
|<xref:Microsoft.Build.Tasks.GenerateManifestBase.Platform%2A>|Doit être **AnyCPU**, **x86**, **x64** ou **Itanium**.  Une chaîne vide est acceptée.|  
|<xref:Microsoft.Build.Tasks.GenerateManifestBase.TargetCulture%2A>|Ce peut être une chaîne vide.  Peut également être une culture neutre \(spécifiée uniquement par le code de langue à deux lettres minuscules par exemple, "jp" pour le japonais\).  Sinon, cette valeur présente les mêmes spécifications que <xref:System.Globalization.CultureInfo.%23ctor%2A>.|  
|<xref:Microsoft.Build.Tasks.GenerateDeploymentManifest.UpdateMode%2A>|Doit être **Premier plan** ou **Arrière\-plan**.  Une chaîne vide est acceptée.|  
|<xref:Microsoft.Build.Tasks.GenerateDeploymentManifest.UpdateUnit%2A>|Doit être **Heures,jours**ou **Semaines**.  Une chaîne vide est acceptée.|  
  
## Voir aussi  
 <xref:Microsoft.Build.Tasks.Deployment.ManifestUtilities.ApplicationManifest.HostInBrowser%2A>   
 <xref:Microsoft.Build.Tasks.GenerateApplicationManifest.TargetFrameworkVersion%2A>   
 [Référence du schéma de produit et de package](../Topic/Product%20and%20Package%20Schema%20Reference.md)   
 [Page Publier, Concepteur de projets](../Topic/Publish%20Page,%20Project%20Designer.md)   
 [MSBuild Error MSB3116](../misc/msbuild-error-msb3116.md)   
 [MSBuild Error MSB3117](../misc/msbuild-error-msb3117.md)   
 [MSBuild Error MSB3118](../misc/msbuild-error-msb3118.md)   
 [MSBuild Error MSB3185](../misc/msbuild-error-msb3185.md)