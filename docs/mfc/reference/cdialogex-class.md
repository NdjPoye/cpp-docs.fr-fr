---
title: "CDialogEx Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDialogEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDialogEx class"
  - "CDialogEx::PreTranslateMessage method"
ms.assetid: a6ed3b1f-aef8-4b66-ac78-2160faf63c13
caps.latest.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CDialogEx Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe `CDialogEx` spécifie la couleur d'arrière\-plan et l'image d'arrière\-plan d'une boîte de dialogue.  
  
## Syntaxe  
  
```  
class CDialogEx : public CDialog  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CDialogEx::CDialogEx](../Topic/CDialogEx::CDialogEx.md)|Construit un objet `CDialogEx`.|  
|`CDialogEx::~CDialogEx`|Destructeur.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDialogEx::SetBackgroundColor](../Topic/CDialogEx::SetBackgroundColor.md)|Définit la couleur d'arrière\-plan de la boîte de dialogue.|  
|[CDialogEx::SetBackgroundImage](../Topic/CDialogEx::SetBackgroundImage.md)|Définit l'image d'arrière\-plan de la boîte de dialogue.|  
  
## Notes  
 Pour utiliser la classe `CDialogEx`, dérivez votre classe de boîte de dialogue de la classe `CDialogEx` plutôt que de la classe `CDialog`.  
  
 Les images de boîte de dialogue sont stockées dans un fichier de ressources.  Le framework supprime automatiquement toute image qui est chargée à partir du fichier de ressources.  Pour supprimer par programmation l'image d'arrière\-plan actuelle, appelez la méthode [CDialogEx::SetBackgroundImage](../Topic/CDialogEx::SetBackgroundImage.md) ou implémentez un gestionnaire d'événements `OnDestroy`.  Quand vous appelez la méthode [CDialogEx::SetBackgroundImage](../Topic/CDialogEx::SetBackgroundImage.md), passez un paramètre `HBITMAP` en tant que descripteur de l'image.  L'objet `CDialogEx` prend possession de l'image et la supprime si l'indicateur `m_bAutoDestroyBmp` a pour valeur `TRUE`.  
  
 Un objet `CDialogEx` peut être parent d'un objet [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md).  L'objet [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md) appelle la méthode `CDialogEx::SetActiveMenu` à l'ouverture de l'objet [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md).  Ensuite, l'objet `CDialogEx` gère les événements de menu jusqu'à la fermeture de l'objet [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
## Configuration requise  
 **En\-tête :** afxdialogex.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md)   
 [CContextMenuManager Class](../../mfc/reference/ccontextmenumanager-class.md)