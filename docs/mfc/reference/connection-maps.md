---
title: "Tables de connexions | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.maps"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tables de connexions"
ms.assetid: 1f25a9bc-6d09-4614-99cf-dc38e8ddfa73
caps.latest.revision: 12
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Tables de connexions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les contrôles OLE peuvent exposer des interfaces à d'autres applications.  Ces interfaces permettent uniquement l'accès d'un conteneur à ce contrôle.  Si un contrôle utilisateur souhaite accéder aux interfaces externes d'autres objets OLE, un point de connexion doit être établi.  Ce point de connexion permet à un contrôle d'accéder à des tables de dispatch externes, telles que les tables d'événements ou les fonctions de notification.  
  
 La bibliothèque MFC offre un modèle de programmation qui prend en charge les points de connexion.  Dans ce modèle, les « mappages de connexions » désignent les interfaces ou points de connexion pour le contrôle OLE.  Les mappages de connexions contiennent une macro pour chaque point de connexion.  Pour plus d'informations sur les mappages de connexion, consultez la classe [CConnectionPoint](../../mfc/reference/cconnectionpoint-class.md).  
  
 En général, un contrôle prend en charge uniquement deux points de connexion : un pour les événements et un pour les notifications de propriété.  Ils sont implémentés par la classe de base `COleControl` et ne requièrent aucun travail supplémentaire par l'enregistreur de contrôle.  Tous les points de connexion supplémentaires à l'implémentation de votre classe doivent être ajoutés manuellement.  Pour prendre en charge des cartes de connexions et des points, MFC fournit les macros suivantes :  
  
### Déclaration et démarcation du mappage de connexions  
  
|||  
|-|-|  
|[BEGIN\_CONNECTION\_PART](../Topic/BEGIN_CONNECTION_PART.md)|Déclare une classe incorporée qui implémente un délai de connexion supplémentaire \(doit être utilisé dans la déclaration de classe\).|  
|[END\_CONNECTION\_PART](../Topic/END_CONNECTION_PART.md)|Termine la déclaration d'un point de connexion \(doit être utilisé dans la déclaration de classe\).|  
|[CONNECTION\_IID](../Topic/CONNECTION_IID.md)|Spécifie l'ID d'interface du point de connexion du contrôle.|  
|[DECLARE\_CONNECTION\_MAP](../Topic/DECLARE_CONNECTION_MAP.md)|Indique qu'une carte de connexions est utilisée dans une classe \(doit être utilisé dans la déclaration de classe\).|  
|[BEGIN\_CONNECTION\_MAP](../Topic/BEGIN_CONNECTION_MAP.md)|Démarre la définition d'une carte de connexion \(doit être utilisé dans l'implémentation de classe\).|  
|[END\_CONNECTION\_MAP](../Topic/END_CONNECTION_MAP.md)|Termine la définition d'une carte de connexion \(doit être utilisé dans l'implémentation de classe\).|  
|[CONNECTION\_PART](../Topic/CONNECTION_PART.md)|Spécifie un point de connexion dans la carte de connexions du contrôle.|  
  
 Les fonctions suivantes assistent un récepteur dans l'établissement et l'arrêt d'une connexion en utilisant des points de connexion :  
  
### Initialisation\/désactivation des points de connexion  
  
|||  
|-|-|  
|[AfxConnectionAdvise](../Topic/AfxConnectionAdvise.md)|Établit une connexion entre une source et un récepteur.|  
|[AfxConnectionUnadvise](../Topic/AfxConnectionUnadvise.md)|Arrête une connexion entre une source et un récepteur.|  
  
## Voir aussi  
 [Macros et objet Globals](../../mfc/reference/mfc-macros-and-globals.md)