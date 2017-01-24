---
title: "VSPackages et infrastructure de package g&#233;r&#233;e | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "infrastructure de package gérée"
  - "VSPackages, infrastructure de package gérée"
  - "VSPackages gérés, infrastructure de package gérée"
ms.assetid: e8d80e0f-6b5b-4baf-a7df-59fd808c60cd
caps.latest.revision: 16
caps.handback.revision: 16
manager: "douge"
---
# VSPackages et infrastructure de package g&#233;r&#233;e
Vous pouvez réduire le temps de développement en créant un VSPackage avec les classes managées \(MPF\) du package plutôt qu'en utilisant des classes COM Interop.  
  
 Il existe deux façons de créer un VSPackage managé :  
  
-   Utilisez le modèle de projet package de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]  
  
     Pour plus d'informations, consultez [Procédure pas à pas : création d’une commande de menu à l’aide du modèle de package Visual Studio](../Topic/Walkthrough:%20Creating%20a%20Menu%20Command%20By%20Using%20the%20Visual%20Studio%20Package%20Template.md).  
  
-   générez votre VSPackage sans modèle de projet de package de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]  
  
     Par exemple, vous pouvez copier un exemple VSPackage et modifier les GUID et les noms.  Vous pouvez rechercher des exemples de la section VSX de [Code Gallery](http://code.msdn.microsoft.com/vsx/).  
  
## Dans cette section  
 [Classes MPF \(Managed Package Framework\)](../misc/managed-package-framework-classes.md)  
 Décrit et répertorie les espaces de noms et les fichiers DLL de classe de MPF.  
  
## Rubriques connexes  
 [Procédure pas à pas : création d’une commande de menu à l’aide du modèle de package Visual Studio](../Topic/Walkthrough:%20Creating%20a%20Menu%20Command%20By%20Using%20the%20Visual%20Studio%20Package%20Template.md)  
 explique comment créer un VSPackage managé.  
  
 [VSPackages gérés](../misc/managed-vspackages.md)  
 Présente les aspects de VSPackages qui s'appliquent au code managé.