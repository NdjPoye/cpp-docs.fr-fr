---
title: "Accessing Version Information from Within Your Program | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.version"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VerQueryValue"
  - "version information, accessing from within programs"
  - "GetFileVersionInfo"
  - "version information"
ms.assetid: 18622333-d9e8-4309-9465-677cd10c79b1
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Accessing Version Information from Within Your Program
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### Pour accéder aux informations de version à partir de votre programme  
  
1.  Si vous souhaitez accéder aux informations de version à partir de votre programme, utilisez les fonctions [GetFileVersionInfo](http://msdn.microsoft.com/library/windows/desktop/ms647003.aspx) et [VerQueryValue](http://msdn.microsoft.com/library/windows/desktop/ms647464.aspx).  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l’ajout de fichiers de ressources aux projets managés, l’accès aux ressources, l’affichage de ressources statiques et l’assignation de chaînes de ressources à des propriétés, et ceci manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Spécifications**  
  
 Win32  
  
## Voir aussi  
 [Version Information Editor](../mfc/version-information-editor.md)   
 [Informations de version \(Windows\)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)