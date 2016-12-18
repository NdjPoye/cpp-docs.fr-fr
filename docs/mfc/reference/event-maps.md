---
title: "Tables d&#39;&#233;v&#233;nements | Microsoft Docs"
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
  - "tables d'événements"
ms.assetid: 1ed53aee-bc53-43cd-834a-6fb935c0d29b
caps.latest.revision: 15
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Tables d&#39;&#233;v&#233;nements
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Chaque fois qu'un contrôle souhaite indiquer à son conteneur qu'une action \(déterminée par le développeur de contrôle\) s'est produite \(par exemple une combinaison de touches, le bouton de la souris, ou une modification à l'état de contrôle\) elle appelle une fonction de déclenchement d'un événement.  Cette fonction notifie le conteneur de contrôle qu'une action importante s'est produite en déclenchant l'événement associé.  
  
 La bibliothèque MFC offre un modèle de programmation optimisé pour déclencher des événements.  Dans ce modèle, des « tables d'événements » sont utilisées pour indiquer quelles sont les fonctions qui déclenchent quels événements pour un contrôle donné.  Les tables d'événements contiennent une macro pour chaque événement.  Par exemple, une table d'événement qui déclenche un événement Clic pourrait se présenter comme suit :  
  
 [!code-cpp[NVC_MFCAxCtl#16](../../mfc/reference/codesnippet/CPP/event-maps_1.cpp)]  
  
 La macro **EVENT\_STOCK\_CLICK** indique que le contrôle déclenche un événement Clic chaque fois qu'il détecte un clic de souris.  Pour une liste plus détaillée d'autres événements types, consultez l'article [Contrôles ActiveX : Événements](../../mfc/mfc-activex-controls-events.md).  Les macros sont également disponibles pour afficher les événements personnalisés.  
  
 Bien que les macros de table d'événements sont importantes, on ne les insère généralement pas directement.  Ceci est dû au fait que la fenêtre Propriétés crée automatiquement des entrées dans la table des messages dans vos fichiers sources lorsque vous l'utilisez pour associer des fonctions de de déclenchement de messages avec des messages.  Lorsque vous souhaitez modifier ou ajouter une entrée dans la table des événements, utilisez la fenêtre Propriétés.  
  
 Pour prendre en charge les tables d'événements, MFC fournit les macros suivantes :  
  
### Déclaration et démarcation de table d'événement  
  
|||  
|-|-|  
|[DECLARE\_EVENT\_MAP](../Topic/DECLARE_EVENT_MAP.md)|Indique qu'une table d'événements est utilisée dans une classe pour faire correspondre les événements des fonctions de déclenchement d'événements \(doit être utilisé dans la déclaration de classe\).|  
|[BEGIN\_EVENT\_MAP](../Topic/BEGIN_EVENT_MAP.md)|Démarre la définition d'une table d'événement \(doit être utilisé dans l'implémentation de classe\).|  
|[END\_EVENT\_MAP](../Topic/END_EVENT_MAP.md)|Termine la définition d'une table d'événement \(doit être utilisé dans l'implémentation de classe\).|  
  
### Macros de mappage d'événement  
  
|||  
|-|-|  
|[EVENT\_CUSTOM](../Topic/EVENT_CUSTOM.md)|Indique que la fonction de déclenchement d'un événement déclenche l'événement spécifié.|  
|[EVENT\_CUSTOM\_ID](../Topic/EVENT_CUSTOM_ID.md)|Indique que la fonction de déclenchement d'un événement déclenche l'événement spécifié, avec un ID d'expédition indiqué.|  
  
### macros de mappage des messages  
  
|||  
|-|-|  
|[ON\_OLEVERB](../Topic/ON_OLEVERB.md)|Indique un verbe personnalisé géré par le contrôle OLE.|  
|[ON\_STDOLEVERB](../Topic/ON_STDOLEVERB.md)|Remplace un mappage standard de verbe du contrôle OLE.|  
  
## Voir aussi  
 [Macros et objet Globals](../../mfc/reference/mfc-macros-and-globals.md)