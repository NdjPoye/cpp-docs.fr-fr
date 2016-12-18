---
title: "Kit de d&#233;veloppement logiciel Visual Studio (SDK) et code manag&#233; | Microsoft Docs"
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
  - "VSIP, à propos du code managé"
ms.assetid: 16b3d88e-b5d8-49a5-a5d7-07cbb0b7e4fc
caps.latest.revision: 20
caps.handback.revision: 20
manager: "douge"
---
# Kit de d&#233;veloppement logiciel Visual Studio (SDK) et code manag&#233;
Le*code managé* est du code écrit dans n'importe quel langage ciblant le common \(CLR\) langage runtime, tels que [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)], [!INCLUDE[csprcs](../ide/includes/csprcs_md.md)], ou [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)].  Quel que soit le langage dans lequel il est écrit dans, tout le code managé est compilé en langage MSIL \(Microsoft Intermediate langage\) au lieu du code natif.  
  
## Prise en charge de l'environnement de VSPackages managé  
 pour prendre en charge créer un VSPackage ou un projet avec un langage managé tel que [!INCLUDE[csprcs](../ide/includes/csprcs_md.md)], [!INCLUDE[vsipsdk](../mfc/includes/vsipsdk_md.md)] fournit ce qui suit :  
  
-   Les assemblys d'interopérabilité de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)], qui activent les VSPackages écrit en code managé d'interagir avec \(COM\) l'environnement de développement intégré \(IDE\) non managé de \(IDE\) [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] .  Pour plus d'informations, consultez [À l'aide d'assemblys PIA de Visual Studio](../Topic/Using%20Visual%20Studio%20Interop%20Assemblies.md).  
  
-   Un jeu de classes managées du package \(MPF\) qui fournit une abstraction de plus haut niveau pour utiliser [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] l'IDE.  Ces classes encapsulent certaines le plus souvent des interfaces utilisées et dans des assemblys d'interopérabilité de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  Ils réduisent considérablement la quantité de travail que vous devez effectuer pour fournir des fonctionnalités de base d'un VSPackage ou d'un projet.  Pour plus d'informations, consultez [Classes MPF \(Managed Package Framework\)](../misc/managed-package-framework-classes.md).  
  
-   Un ensemble d'exemples de base d'un VSPackage écrits en code managé.  Les exemples managés reposent sur un exemple d'un simple, entièrement \- VSPackage fonctionnel pour afficher un éditeur de base, une fenêtre Outil, un extendeur d'objet, et d'autres composants.  Pour plus d'informations, consultez [Exemples d’extensibilité Visual Studio](../misc/vssdk-samples.md).  
  
## Voir aussi  
 [VSPackages gérés](../misc/managed-vspackages.md)   
 [À l'aide d'assemblys PIA de Visual Studio](../Topic/Using%20Visual%20Studio%20Interop%20Assemblies.md)   
 [Classes MPF \(Managed Package Framework\)](../misc/managed-package-framework-classes.md)