---
title: "CDialogBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDialogBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDialogBar class"
  - "dialog bars, Windows modeless dialog box"
  - "boîtes de dialogue, non modales"
ms.assetid: da2f7a30-970c-44e3-87f0-6094bd002cab
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CDialogBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités d'une boîte de dialogue non modale windows dans une barre de contrôles.  
  
## Syntaxe  
  
```  
class CDialogBar : public CControlBar  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CDialogBar::CDialogBar](../Topic/CDialogBar::CDialogBar.md)|Construit un objet `CDialogBar`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDialogBar::Create](../Topic/CDialogBar::Create.md)|Crée une barre de boîte de dialogue windows et l'attache à l'objet d' `CDialogBar` .|  
  
## Notes  
 Une barre de boîte de dialogue ressemble à une boîte de dialogue parce qu'elle contient des contrôles Windows standard que l'utilisateur peut tabuler entre.  Une autre ressemblance est que vous créez un modèle de boîte de dialogue pour représenter la barre de boîte de dialogue.  
  
 Création et utilisation d'une barre de boîte de dialogue est semblable à créer et à utiliser un objet d' `CFormView` .  D'abord, utilisez [éditeur de boîtes de dialogue](../../mfc/dialog-editor.md) pour définir un modèle de boîte de dialogue avec le style **WS\_CHILD** et aucun style.  Le modèle ne doit pas avoir le style **WS\_VISIBLE**.  Dans votre code d'application, appelez le constructeur pour construire l'objet d' `CDialogBar` , puis appelez **Créer** pour créer la fenêtre de la barre de boîte de dialogue et pour la liaison à l'objet d' `CDialogBar` .  
  
 Pour plus d'informations sur `CDialogBar`, consultez l'article [Barre de boîte de dialogue](../../mfc/dialog-bars.md) et [note technique 31](../../mfc/tn031-control-bars.md), barres de contrôles.  
  
> [!NOTE]
>  Dans la version actuelle, un objet d' `CDialogBar` ne peut pas héberger de contrôles Windows Forms.  Pour plus d'informations sur les contrôles Windows Forms dans Visual C\+\+, consultez l' [Utilisation d'un contrôle utilisateur Windows Form dans MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CDialogBar`  
  
## Configuration requise  
 **Header:** afxext.h  
  
## Voir aussi  
 [CTRLBARS exemple MFC](../../top/visual-cpp-samples.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CFormView Class](../../mfc/reference/cformview-class.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)