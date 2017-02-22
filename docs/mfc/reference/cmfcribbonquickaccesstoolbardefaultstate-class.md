---
title: "CMFCRibbonQuickAccessToolBarDefaultState Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonQuickAccessToolBarDefaultState"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonQuickAccessToolBarDefaultState class"
ms.assetid: eca99200-b87b-47ba-b2e8-2f3f2444b176
caps.latest.revision: 28
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 30
---
# CMFCRibbonQuickAccessToolBarDefaultState Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une classe d'assistance qui gère l'état par défaut de la Barre d'outils Accès rapide qui est située dans la barre de ruban \([CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md)\).  
  
## Syntaxe  
  
```  
class CMFCRibbonQuickAccessToolBarDefaultState  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState](../Topic/CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState.md)|Construit un objet `CMFCRibbonQuickAccessToolbarDefaultState`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](../Topic/CMFCRibbonQuickAccessToolBarDefaultState::AddCommand.md)|Ajoute une commande à l'état par défaut de la Barre d'outils Accès rapide.  Cela ne change pas la barre d'outils elle\-même.|  
|[CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom](../Topic/CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom.md)|Copie les propriétés d'une Barre d'outils Accès rapide à un autre.|  
|[CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll](../Topic/CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll.md)|Supprime toutes les commandes de la Barre d'outils Accès rapide.  Cela ne change pas la barre d'outils elle\-même.|  
  
## Notes  
 Après avoir créé la Barre d'outils Accès rapide dans votre application, il est recommandé de définir son état par défaut en appelant [CMFCRibbonBar::SetQuickAccessDefaultState](../Topic/CMFCRibbonBar::SetQuickAccessDefaultState.md).  Cet état par défaut est restauré lorsqu'un utilisateur clique sur le bouton **Réinitialiser** sur la page **Personnaliser** de la boîte de dialogue **Options** de votre application.  
  
## Hiérarchie d'héritage  
 [CMFCRibbonQuickAccessToolBarDefaultState](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md)  
  
## Exemple  
 L'exemple suivant montre comment construire un objet avec de la classe d' `CMFCRibbonQuickAccessToolbarDefaultState` et comment ajouter une commande à l'état par défaut de la Barre d'outils Accès rapide.  
  
 [!code-cpp[NVC_MFC_RibbonApp#21](../../mfc/reference/codesnippet/CPP/cmfcribbonquickaccesstoolbardefaultstate-class_1.cpp)]  
  
## Configuration requise  
 **en\-tête :** afxribbonquickaccesstoolbar.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md)   
 [CMFCRibbonBar::SetQuickAccessDefaultState](../Topic/CMFCRibbonBar::SetQuickAccessDefaultState.md)