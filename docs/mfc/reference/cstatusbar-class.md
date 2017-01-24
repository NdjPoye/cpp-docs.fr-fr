---
title: "CStatusBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CStatusBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStatusBar class"
  - "indicators"
  - "indicators, status bar"
  - "barres d'état"
  - "status indicators"
ms.assetid: a3bde3db-e71c-4881-a3ca-1d5481c345ba
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CStatusBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une barre de contrôles avec une ligne de texte a sorti des volets, ou « indicateurs ».  
  
## Syntaxe  
  
```  
class CStatusBar : public CControlBar  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CStatusBar::CStatusBar](../Topic/CStatusBar::CStatusBar.md)|Construit un objet `CStatusBar`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CStatusBar::CommandToIndex](../Topic/CStatusBar::CommandToIndex.md)|Obtient l'index pour une application donnée d'indicateur|  
|[CStatusBar::Create](../Topic/CStatusBar::Create.md)|Crée la barre d'état, la attaché à l'objet d' `CStatusBar` , et définit la hauteur initiale de police et de barre.|  
|[CStatusBar::CreateEx](../Topic/CStatusBar::CreateEx.md)|Crée un objet d' `CStatusBar` avec les styles supplémentaires pour l'objet incorporé d' `CStatusBarCtrl` .|  
|[CStatusBar::DrawItem](../Topic/CStatusBar::DrawItem.md)|Appelé lorsqu'un aspect visuel s'aligne d'un contrôle de barre d'état owner draw.|  
|[CStatusBar::GetItemID](../Topic/CStatusBar::GetItemID.md)|Obtient l'ID d'indicateur pour un index donné.|  
|[CStatusBar::GetItemRect](../Topic/CStatusBar::GetItemRect.md)|Obtient le rectangle d'affichage pour un index donné.|  
|[CStatusBar::GetPaneInfo](../Topic/CStatusBar::GetPaneInfo.md)|Obtient l'ID, le style, et la largeur des indicateurs pour un index donné.|  
|[CStatusBar::GetPaneStyle](../Topic/CStatusBar::GetPaneStyle.md)|Obtient le style des indicateurs pour un index donné.|  
|[CStatusBar::GetPaneText](../Topic/CStatusBar::GetPaneText.md)|Obtient le texte de l'indicateur pour un index donné.|  
|[CStatusBar::GetStatusBarCtrl](../Topic/CStatusBar::GetStatusBarCtrl.md)|Autorise l'accès direct au contrôle commun sous\-jacent.|  
|[CStatusBar::SetIndicators](../Topic/CStatusBar::SetIndicators.md)|Définit les ID des indicateurs.|  
|[CStatusBar::SetPaneInfo](../Topic/CStatusBar::SetPaneInfo.md)|Définit l'ID, le style, et la largeur des indicateurs pour un index donné.|  
|[CStatusBar::SetPaneStyle](../Topic/CStatusBar::SetPaneStyle.md)|Définit le style des indicateurs pour un index donné.|  
|[CStatusBar::SetPaneText](../Topic/CStatusBar::SetPaneText.md)|Définit le texte d'indicateur pour un index donné.|  
  
## Notes  
 Les volets de sortie en général sont utilisés comme lignes de message et comme indicateurs.  Les exemples incluent les lignes d'aide\- message de menu qui présentent brièvement la commande de menu sélectionné et les indicateurs qui illustrent le mode du DÉFIL, VERR.NUM le, et les deux clés.  
  
 [CStatusBar::GetStatusBarCtrl](../Topic/CStatusBar::GetStatusBarCtrl.md), une fonction membre nouvelle aux MFC 4,0, vous permet de tirer parti de la prise en charge de contrôles communs Windows à la personnalisation et de la fonctionnalité supplémentaire de barre d'état.  Les fonctions membres d'`CStatusBar` vous fournissent plus de les fonctionnalités des contrôles communs Windows ; toutefois, lorsque vous appelez `GetStatusBarCtrl`, vous pouvez permettre à vos barres d'état bien plus les caractéristiques d'une barre d'état Windows 95\/98.  Lorsque vous appelez `GetStatusBarCtrl`, il retourne une référence à un objet d' `CStatusBarCtrl` .  Consultez [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) pour plus d'informations sur la conception de barres d'outils à des contrôles communs Windows.  Pour plus d'informations générales sur les contrôles communs, consultez [contrôles communs](http://msdn.microsoft.com/library/windows/desktop/bb775493) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 L'infrastructure stocke les informations d'indicateur dans un tableau avec l'indicateur situé le plus à gauche à la position 0.  Lorsque vous créez une barre d'état, utilisez un tableau d'ID de chaîne que l'infrastructure rapport avec les indicateurs correspondants.  Vous pouvez ensuite utiliser un ID de chaîne ou un index pour accéder à un indicateur.  
  
 Par défaut, le premier indicateur est « élastique » : il prend la longueur de barre d'état non utilisée par les autres volets des indicateurs, afin que les autres volets sont alignés à droite.  
  
 Pour créer une barre d'état, suivez ces étapes :  
  
1.  Construisez l'objet d' `CStatusBar` .  
  
2.  Appelez la fonction de [Create](../Topic/CStatusBar::Create.md) \(ou [CreateEx](../Topic/CStatusBar::CreateEx.md)\) pour créer la fenêtre de barre d'état et pour la liaison à l'objet d' `CStatusBar` .  
  
3.  Appelez [SetIndicators](../Topic/CStatusBar::SetIndicators.md) pour associer un ID de chaîne avec chaque indicateur.  
  
 Il existe trois façons de mettre à jour le texte d'un volet de barre d'état :  
  
1.  Appel [CWnd::SetWindowText](../Topic/CWnd::SetWindowText.md) pour mettre à jour le texte dans le volet 0 uniquement.  
  
2.  Appel [CCmdUI::SetText](../Topic/CCmdUI::SetText.md) dans le gestionnaire d' `ON_UPDATE_COMMAND_UI` de la barre d'état.  
  
3.  Appel [SetPaneText](../Topic/CStatusBar::SetPaneText.md) pour mettre à jour le texte pour tout volet.  
  
 Appel [SetPaneStyle](../Topic/CStatusBar::SetPaneStyle.md) pour mettre à jour le style d'un volet de barre d'état.  
  
 Pour plus d'informations sur l'utilisation `CStatusBar`, consultez l'article [Implémentation de barre d'état dans MFC](../../mfc/status-bar-implementation-in-mfc.md) et [note technique 31 : barres de contrôles](../../mfc/tn031-control-bars.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CStatusBar`  
  
## Configuration requise  
 **Header:** afxext.h  
  
## Voir aussi  
 [CTRLBARS exemple MFC](../../top/visual-cpp-samples.md)   
 [MFC exemple DLGCBR32](../../top/visual-cpp-samples.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CStatusBarCtrl Class](../../mfc/reference/cstatusbarctrl-class.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)   
 [CWnd::SetWindowText](../Topic/CWnd::SetWindowText.md)   
 [CStatusBar::SetIndicators](../Topic/CStatusBar::SetIndicators.md)