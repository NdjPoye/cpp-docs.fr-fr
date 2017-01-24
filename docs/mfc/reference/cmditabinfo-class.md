---
title: "CMDITabInfo Class | Microsoft Docs"
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
  - "CMDITabInfo"
  - "CMDITabInfo.CMDITabInfo"
  - "CMDITabInfo::CMDITabInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMDITabInfo class"
  - "CMDITabInfo class, constructeur"
ms.assetid: 988ae1b7-4f7f-4239-b88f-7e28b3291c5e
caps.latest.revision: 37
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMDITabInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMDITabInfo` est utilisée pour passer des paramètres à la méthode de [CMDIFrameWndEx::EnableMDITabbedGroups](../Topic/CMDIFrameWndEx::EnableMDITabbedGroups.md) .  Définissez les membres de cette classe pour contrôler le comportement MDI est tabulé des groupes.  
  
## Syntaxe  
  
```  
class CMDITabInfo   
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`CMDITabInfo::CMDITabInfo`|Constructeur par défaut.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMDITabInfo::Serialize](../Topic/CMDITabInfo::Serialize.md)|Lit ou écrit cet objet ou y retourne une archive.|  
  
### Membres de données  
  
|Nom|Description|  
|---------|-----------------|  
|[CMDITabInfo::m\_bActiveTabCloseButton;](../Topic/CMDITabInfo::m_bActiveTabCloseButton;.md)|Spécifie si un bouton **Fermer** s'affiche dans l'étiquette de l'onglet actif.|  
|[CMDITabInfo::m\_bAutoColor](../Topic/CMDITabInfo::m_bAutoColor.md)|Spécifie si les couleurs onglets MDI.|  
|[CMDITabInfo::m\_bDocumentMenu](../Topic/CMDITabInfo::m_bDocumentMenu.md)|Spécifie si le groupe d'onglets affiche un menu contextuel qui affiche une liste de documents ouverts ou affiche les boutons de défilement.|  
|[CMDITabInfo::m\_bEnableTabSwap](../Topic/CMDITabInfo::m_bEnableTabSwap.md)|Spécifie si l'utilisateur peut échanger les positions des onglets en la faisant glisser.|  
|[CMDITabInfo::m\_bFlatFrame](../Topic/CMDITabInfo::m_bFlatFrame.md)|Spécifie si les onglets ont un frame en deux dimensions.|  
|[CMDITabInfo::m\_bTabCloseButton](../Topic/CMDITabInfo::m_bTabCloseButton.md)|Spécifie si chaque étiquette d'onglet affiche un bouton **Fermer** .|  
|[CMDITabInfo::m\_bTabCustomTooltips](../Topic/CMDITabInfo::m_bTabCustomTooltips.md)|Spécifie si les info\-bulles personnalisées sont activées.|  
|[CMDITabInfo::m\_bTabIcons](../Topic/CMDITabInfo::m_bTabIcons.md)|Spécifie s'il faut afficher des icônes sur les onglets MDI.|  
|[CMDITabInfo::m\_nTabBorderSize](../Topic/CMDITabInfo::m_nTabBorderSize.md)|Spécifie la taille de la bordure de chaque fenêtre d'onglet.|  
|[CMDITabInfo::m\_style](../Topic/CMDITabInfo::m_style.md)|Spécifie le style des étiquettes d'onglet.|  
|[CMDITabInfo::m\_tabLocation](../Topic/CMDITabInfo::m_tabLocation.md)|Spécifie si les étiquettes d'onglets sont situées en haut ou en bas de la page.|  
  
## Notes  
 Cette classe spécifie les paramètres des groupes d'onglets MDI de l'infrastructure crée.  
  
## Exemple  
 L'exemple suivant montre comment définir les valeurs des différentes variables membres dans la classe d' `CMDITabInfo` .  
  
 [!code-cpp[NVC_MFC_MDITab#1](../../mfc/reference/codesnippet/CPP/cmditabinfo-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CMDITabInfo](../../mfc/reference/cmditabinfo-class.md)  
  
## Configuration requise  
 **en\-tête :** afxmdiclientareawnd.h  
  
## Voir aussi  
 [Classe CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md)   
 [Groupes avec onglet MDI](../../mfc/mdi-tabbed-groups.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)