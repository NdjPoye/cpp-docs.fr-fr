---
title: "Contr&#244;le d&#39;application | Microsoft Docs"
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
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "contrôle d'application"
ms.assetid: c1f69f15-e0fe-4515-9f36-d63d31869deb
caps.latest.revision: 12
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Contr&#244;le d&#39;application
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE requiert un contrôle important sur les applications et leurs objets.  Les DLL système OLE doivent pouvoir exécuter et de libérer des applications automatiquement, coordonner la production et modification des objets, etc.  Les fonctions de cette rubrique répondent à ces critères.  En plus d'être appelées par les DLL système OLE, elles doivent parfois être appelée par les applications.  
  
### Contrôle d'application  
  
|||  
|-|-|  
|[AfxOleCanExitApp](../Topic/AfxOleCanExitApp.md)|Indique si l'application peut se terminer.|  
|[AfxOleGetMessageFilter](../Topic/AfxOleGetMessageFilter.md)|Récupère le filtre de message actuel de l'application.|  
|[AfxOleGetUserCtrl](../Topic/AfxOleGetUserCtrl.md)|Récupère l'indicateur de contrôle utilisateur actuel.|  
|[AfxOleSetUserCtrl](../Topic/AfxOleSetUserCtrl.md)|Définit ou désactive l'indicateur du contrôle utilisateur.|  
|[AfxOleLockApp](../Topic/AfxOleLockApp.md)|Incrémente le compteur global du framework du nombre d'objets actifs dans une application.|  
|[AfxOleUnlockApp](../Topic/AfxOleUnlockApp.md)|Décrémente le compteur global du framework du nombre d'objets actifs dans une application.|  
|[AfxOleRegisterServerClass](../Topic/AfxOleRegisterServerClass.md)|Inscrit un serveur dans le Registre système OLE.|  
|[AfxOleSetEditMenu](../Topic/AfxOleSetEditMenu.md)|Implémente l'interface utilisateur pour la commande de l'objet *typename*.|  
  
## Voir aussi  
 [Macros et objet Globals](../../mfc/reference/mfc-macros-and-globals.md)