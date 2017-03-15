---
title: "Manifest Resources | Microsoft Docs"
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
  - "manifest resources"
  - "resources [Visual Studio], manifest"
ms.assetid: 8615334c-22a0-44c0-93e0-5924528c9917
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Manifest Resources
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les ressources de manifeste sont des fichiers XML qui décrivent les dépendances qu'une application utilise. Par exemple, dans Visual Studio, le fichier manifeste généré par l'Assistant MFC définit la DLL de contrôle commun Windows que l'application doit utiliser, version 5.0 ou 6.0 :  
  
```  
<description>Your app description here</description> <dependency> <dependentAssembly> <assemblyIdentity type="win32" name="Microsoft.Windows.Common-Controls" version="6.0.0.0" processorArchitecture="X86" publicKeyToken="6595b64144ccf1df" language="*" /> </dependentAssembly> </dependency>   
```  
  
 Pour une application Windows XP ou Windows Vista, la ressource de manifeste indique non seulement que l’application utilise la toute dernière version des contrôles communs Windows \(v6.0, comme indiqué ci\-dessus\) mais qu’elle prend également en charge le nouveau [contrôle Syslink](http://msdn.microsoft.com/library/windows/desktop/bb760706).  
  
 Pour afficher les informations de version et de type contenues dans une ressource de manifeste, vous pouvez ouvrir le fichier dans une visionneuse XML ou dans l'[Éditeur de texte](http://msdn.microsoft.com/fr-fr/508e1f18-99d5-48ad-b5ad-d011b21c6ab1) Visual Studio. Pour plus d'informations, voir [Ouverture d'une ressource de manifeste dans l'éditeur de texte Visual Studio](../windows/how-to-open-a-manifest-resource.md).  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour plus d’informations sur l’ajout manuel de fichiers de ressources aux projets managés, l’accès aux ressources, l’affichage de ressources statiques et l’assignation de chaînes de ressources à des propriétés, consultez [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Limitations  
 Vous ne pouvez avoir qu'une seule ressource de manifeste par module.  
  
## Spécifications  
 Win32  
  
## Voir aussi  
 [Contrôles](../mfc/controls-mfc.md)   
 [Working with Resource Files](../mfc/working-with-resource-files.md)