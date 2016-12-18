---
title: "CMFCDisableMenuAnimation Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCDisableMenuAnimation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDisableMenuAnimation class"
ms.assetid: c6eb07da-c382-43d6-8028-007f2320e50e
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCDisableMenuAnimation Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Désactive l'animation de menu contextuel.  
  
## Syntaxe  
  
```  
class CMFCDisableMenuAnimation  
```  
  
## Membres  
  
### Constructeurs publics  
  
|||  
|-|-|  
|Nom|Description|  
|`CMFCDisableMenuAnimation::CMFCDisableMenuAnimation`|Construit un objet `CMFCDisableMenuAnimation`.|  
|`CMFCDisableMenuAnimation::~CMFCDisableMenuAnimation`|Destructor.|  
  
### Méthodes publiques  
  
|||  
|-|-|  
|Nom|Description|  
|[CMFCDisableMenuAnimation::Restore](../Topic/CMFCDisableMenuAnimation::Restore.md)|Restaure l'animation qui la précède cette l'infrastructure utilisée pour afficher un menu contextuel.|  
  
### Membres de données  
  
|||  
|-|-|  
|Nom|Description|  
|`CMFCDisableMenuAnimation::m_animType`|Stocke le type précédent d'animation de menu contextuel.|  
  
### Remarques  
 Utilisez cette classe d'assistance pour désactiver temporairement l'animation de menu contextuel \(par exemple, lorsque vous utilisez des commandes de clavier de souris ou\).  
  
 Un objet d' `CMFCDisableMenuAnimation` désactive l'animation de menu contextuel pendant sa durée de vie.  Le constructeur stocke l'animation actuelle de menu contextuel dans le champ et les jeux d' `m_animType` le type actuel d'animation à `CMFCPopupMenu::NO_ANIMATION`.  Le destructeur restaure le type d'animation précédent.  
  
 Vous pouvez créer un objet d' `CMFCDisableMenuAnimation` sur la pile à l'animation de menu contextuel désactiver de dans toute une fonction unique.  Si vous souhaitez désactiver l'animation de menus instantanée entre les fonctions, créez un objet d' `CMFCDisableMenuAnimation` sur le tas puis supprimez \-le lorsque vous souhaitez restaurer l'animation de menu contextuel.  
  
## Exemple  
 l'exemple suivant montre comment utiliser la pile pour désactiver temporairement l'animation de menus.  
  
 [!code-cpp[NVC_MFC_Misc#1](../../mfc/reference/codesnippet/CPP/cmfcdisablemenuanimation-class_1.h)]  
  
## Hiérarchie d'héritage  
 [CMFCDisableMenuAnimation](../../mfc/reference/cmfcdisablemenuanimation-class.md)  
  
## Configuration requise  
 **en\-tête :** afxpopupmenu.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md)