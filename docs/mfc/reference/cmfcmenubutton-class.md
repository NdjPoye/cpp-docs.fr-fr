---
title: "CMFCMenuButton, Classe | Microsoft Docs"
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
  - "CMFCMenuButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCMenuButton, classe"
ms.assetid: 53d3d459-1e5a-47c5-8b7f-2e61f6af5187
caps.latest.revision: 32
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCMenuButton, Classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Un bouton qui affiche un menu contextuel et des rapports sur les sélections de menu de l'utilisateur.  
  
## Syntaxe  
  
```  
class CMFCMenuButton : public CMFCButton  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCMenuButton::CMFCMenuButton](../Topic/CMFCMenuButton::CMFCMenuButton.md)|Construit un objet `CMFCMenuButton`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCMenuButton::PreTranslateMessage](../Topic/CMFCMenuButton::PreTranslateMessage.md)|Appelé par l'infrastructure pour convertir des messages de fenêtre pour qu'ils soient distribués.  \(Substitutions `CMFCButton::PreTranslateMessage`.\)|  
|[CMFCMenuButton::SizeToContent](../Topic/CMFCMenuButton::SizeToContent.md)|Modifie la taille du bouton en fonction de son texte et sa taille de l'image.|  
  
### Membres de données  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCMenuButton::m\_bOSMenu](../Topic/CMFCMenuButton::m_bOSMenu.md)|Spécifie s'il faut afficher le menu contextuel par défaut du système ou utiliser [CContextMenuManager::TrackPopupMenu](../Topic/CContextMenuManager::TrackPopupMenu.md).|  
|[CMFCMenuButton::m\_bRightArrow](../Topic/CMFCMenuButton::m_bRightArrow.md)|Sous spécifie si le menu contextuel apparaît ou à droite du bouton.|  
|[CMFCMenuButton::m\_bStayPressed](../Topic/CMFCMenuButton::m_bStayPressed.md)|Spécifie si le bouton de menu remplace son état après que l'utilisateur relâche le bouton.|  
|[CMFCMenuButton::m\_hMenu](../Topic/CMFCMenuButton::m_hMenu.md)|Un handle au menu joint.|  
|[CMFCMenuButton::m\_nMenuResult](../Topic/CMFCMenuButton::m_nMenuResult.md)|Un identificateur qui indique que l'élément sélectionné par l'utilisateur dans le menu contextuel.|  
  
## Notes  
 La classe d' `CMFCMenuButton` est dérivée de [CMFCButton Class](../../mfc/reference/cmfcbutton-class.md) qui est ensuite dérivée de [CButton Class](../../mfc/reference/cbutton-class.md).  Par conséquent, vous pouvez utiliser `CMFCMenuButton` dans votre code de la même manière que vous utiliseriez `CButton`.  
  
 Lorsque vous créez `CMFCMenuButton`, vous devez passer dans un handle dans le menu contextuel associé.  Ensuite, appelez la fonction `CMFCMenuButton::SizeToContent`.  `CMFCMenuButton::SizeToContent` vérifie que la taille du bouton est suffisante pour inclure une flèche qui pointe vers l'emplacement où la fenêtre contextuelle apparaît \(à savoir, sous ou à droite du bouton.  
  
## Exemple  
 L'exemple suivant montre comment définir le handle du menu joint au bouton, redimensionner le bouton en fonction de son texte et sa taille de l'image, et définir le menu contextuel qui s'affiche par l'infrastructure.  Cet extrait de code fait partie d' [Nouvel exemples de contrôles](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#38](../../mfc/reference/codesnippet/CPP/cmfcmenubutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#39](../../mfc/reference/codesnippet/CPP/cmfcmenubutton-class_2.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md)  
  
## Configuration requise  
 **En\-tête :** afxmenubutton.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCButton Class](../../mfc/reference/cmfcbutton-class.md)