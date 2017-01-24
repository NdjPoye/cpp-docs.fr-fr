---
title: "Type de projet non disponible | Microsoft Docs"
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
  - "vs.projecttypenotavailable"
helpviewer_keywords: 
  - "Type de projet non disponible (erreur)"
ms.assetid: a579fe75-efa2-4dd0-b5d7-ae106d3aedbd
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Type de projet non disponible
Cette boîte de dialogue apparaît avec l'erreur « Impossible d'ouvrir \<projet\> car son type de projet \<type\_projet\> n'est pas pris en charge par cette version de l'application ».  
  
## Solution de contournement  
  
-   Cette boîte de dialogue apparaît car un produit ou une version de produit nécessaire pour ouvrir le fichier spécifié est introuvable.  Cette erreur se produit couramment si vous tentez d'ouvrir un fichier projet impossible à ouvrir avec la version installée de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  Par exemple, si vous tentez d'ouvrir un fichier projet [!INCLUDE[csprcs](../ide/includes/csprcs_md.md)] avec [!INCLUDE[vbprvbxprlong](../misc/includes/vbprvbxprlong_md.md)], cette boîte de dialogue s'affiche.  
  
#### Pour contourner cette erreur  
  
-   Installez la version correcte de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  
  
## Voir aussi  
 [Portage, migration et mise à niveau des projets Visual Studio](../Topic/Porting,%20Migrating,%20and%20Upgrading%20Visual%20Studio%20Projects.md)   
 [Référence de propriétés de projet](../Topic/Project%20Properties%20Reference.md)