---
title: "Security Global Functions | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ACL object global functions"
  - "security IDs [C++]"
  - "SIDs [C++], modifying SID objects"
ms.assetid: 6a584bfe-16b7-47f4-8439-9c789c41567a
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# Security Global Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ces fonctions fournissent la prise en charge de modifier des objets de SID et de liste de contrôle d'accès.  
  
> [!IMPORTANT]
>  Les fonctions répertoriées dans le tableau suivant ne peuvent pas être utilisées dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[AtlGetDacl](../Topic/AtlGetDacl.md)|Appelez cette fonction pour extraire des informations discrétionnaires de \(DACL\) de liste de contrôle d'accès d'un objet spécifié.|  
|[AtlSetDacl](../Topic/AtlSetDacl.md)|Appelez cette fonction pour définir les informations de discrétionnaires \(DACL\) de liste de contrôle d'accès d'un objet spécifié.|  
|[AtlGetGroupSid](../Topic/AtlGetGroupSid.md)|Appelez cette fonction pour extraire l'identificateur de sécurité de groupe \(SID\) d'un objet.|  
|[AtlSetGroupSid](../Topic/AtlSetGroupSid.md)|Appelez cette fonction pour définir l'identificateur de sécurité de groupe \(SID\) d'un objet.|  
|[AtlGetOwnerSid](../Topic/AtlGetOwnerSid.md)|Appelez cette fonction pour extraire l'identificateur de sécurité \(SID\) de propriétaire d'un objet.|  
|[AtlSetOwnerSid](../Topic/AtlSetOwnerSid.md)|Appelez cette fonction pour définir l'identificateur de sécurité \(SID\) de propriétaire d'un objet.|  
|[AtlGetSacl](../Topic/AtlGetSacl.md)|Appelez cette fonction pour extraire des informations de \(SACL\) de liste de contrôle d'accès système d'un objet spécifié.|  
|[AtlSetSacl](../Topic/AtlSetSacl.md)|Appelez cette fonction pour définir les informations de \(SACL\) de liste de contrôle d'accès système d'un objet spécifié.|  
|[AtlGetSecurityDescriptor](../Topic/AtlGetSecurityDescriptor.md)|Appelez cette fonction pour récupérer le modèle de sécurité d'un objet donné.|  
  
## Voir aussi  
 [Fonctions](../../atl/reference/atl-functions.md)