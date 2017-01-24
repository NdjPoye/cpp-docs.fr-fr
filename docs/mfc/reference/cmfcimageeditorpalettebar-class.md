---
title: "CMFCImageEditorPaletteBar Class | Microsoft Docs"
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
  - "CMFCImageEditorPaletteBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCImageEditorPaletteBar class"
ms.assetid: 3fb7ba8e-f254-4d56-b913-9941b4ed8138
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCImageEditorPaletteBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités de barre de la palette dans une boîte de dialogue d'éditeur d'images.  
  
## Syntaxe  
  
```  
class CMFCImageEditorPaletteBar : public CMFCToolBar  
```  
  
## Membres  
  
### Méthodes publiques  
  
|||  
|-|-|  
|Nom|Description|  
|[CMFCImageEditorPaletteBar::GetRowHeight](../Topic/CMFCImageEditorPaletteBar::GetRowHeight.md)|Retourne la hauteur de boutons de barre d'outils.  \(Substitutions [CMFCToolBar::GetRowHeight](../Topic/CMFCToolBar::GetRowHeight.md).\)|  
|[CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable](../Topic/CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable.md)|Détermine si la barre d'outils peut afficher des boutons qui ont étendu des bordures.  \(Substitutions [CMFCToolBar::IsButtonExtraSizeAvailable](../Topic/CMFCToolBar::IsButtonExtraSizeAvailable.md).\)|  
  
### Remarques  
 Cette classe n'est pas destinée à être utilisée directement à partir de votre code.  
  
 L'infrastructure utilise la classe pour afficher une barre de la palette dans une boîte de dialogue d'éditeur d'images.  Pour plus d'informations sur la boîte de dialogue d'éditeur d'images, consultez [CMFCImageEditorDialog Class](../../mfc/reference/cmfcimageeditordialog-class.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBa](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCImageEditorPaletteBar](../../mfc/reference/cmfcimageeditorpalettebar-class.md)  
  
## Configuration requise  
 **en\-tête :** afximageeditordialog.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCImageEditorDialog Class](../../mfc/reference/cmfcimageeditordialog-class.md)