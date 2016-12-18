---
title: "Registry and TypeLib Global Functions | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RegistryDataExchange function, fonctions globales"
ms.assetid: d58b8a4e-975c-4417-8b34-d3c847f679b3
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Registry and TypeLib Global Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ces fonctions fournissent la prise en charge de charger et d'inscrire une bibliothèque de types.  
  
> [!IMPORTANT]
>  Les fonctions répertoriées dans les tableaux suivants ne peuvent pas être utilisées dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[AtlRegisterTypeLib](../Topic/AtlRegisterTypeLib.md)|Cette fonction est appelée pour inscrire une bibliothèque de types.|  
|[AtlUnRegisterTypeLib](../Topic/AtlUnRegisterTypeLib.md)|Cette fonction est appelée pour annuler l'enregistrement une bibliothèque de types|  
|[AtlLoadTypeLib](../Topic/AtlLoadTypeLib.md)|Cette fonction est appelée pour charger une bibliothèque de types.|  
|[AtlUpdateRegistryFromResourceD](../Topic/AtlUpdateRegistryFromResourceD.md)|Cette fonction est appelée pour mettre à jour le Registre de la ressource fournie.|  
|[RegistryDataExchange](../Topic/RegistryDataExchange.md)|Cette fonction est appelée pour lire, ou écriture, y retourne la base de registres.  Appelé par [Macros d'échange de données de Registre](../../atl/reference/registry-data-exchange-macros.md).|  
  
 Contrôle de ces fonctions que le nœud dans le Registre le programme utilise pour stocker des informations.  
  
|||  
|-|-|  
|[AtlGetPerUserRegistration](../Topic/AtlGetPerUserRegistration.md)|Récupère si l'application redirige l'accès au Registre au nœud d' **HKEY\_CURRENT\_USER** \(**HKCU**\).|  
|[AtlSetPerUserRegistration](../Topic/AtlSetPerUserRegistration.md)|Définit si l'application redirige l'accès au Registre au nœud d' **HKEY\_CURRENT\_USER** \(**HKCU**\).|  
  
## Voir aussi  
 [Fonctions](../../atl/reference/atl-functions.md)