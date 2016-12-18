---
title: "CMFCPreviewCtrlImpl Class | Microsoft Docs"
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
  - "CMFCPreviewCtrlImpl"
  - "afxwin/CMFCPreviewCtrlImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPreviewCtrlImpl class"
ms.assetid: 06257fa0-54c9-478d-9d68-c9698c3f93ed
caps.latest.revision: 28
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCPreviewCtrlImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente une fenêtre définie sur une fenêtre hôte donné par le shell pour l'aperçu riche.  
  
## Syntaxe  
  
```  
class CMFCPreviewCtrlImpl : public CWnd;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCPreviewCtrlImpl::~CMFCPreviewCtrlImpl](../Topic/CMFCPreviewCtrlImpl::~CMFCPreviewCtrlImpl.md)|Détruit un objet contrôle d'aperçu.|  
|[CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl](../Topic/CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl.md)|Construit un objet contrôle d'aperçu.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCPreviewCtrlImpl::Create](../Topic/CMFCPreviewCtrlImpl::Create.md)|Surchargé.  Appelé par un gestionnaire riche d'aperçu pour créer la fenêtre de windows.|  
|[CMFCPreviewCtrlImpl::Destroy](../Topic/CMFCPreviewCtrlImpl::Destroy.md)|Appelé par un gestionnaire riche d'aperçu lorsqu'il doit détruire ce contrôle.|  
|[CMFCPreviewCtrlImpl::Focus](../Topic/CMFCPreviewCtrlImpl::Focus.md)|Définit le focus d'entrée sur ce contrôle.|  
|[CMFCPreviewCtrlImpl::GetDocument](../Topic/CMFCPreviewCtrlImpl::GetDocument.md)|Retourne un document connecté à ce contrôle d'aperçu.|  
|[CMFCPreviewCtrlImpl::Redraw](../Topic/CMFCPreviewCtrlImpl::Redraw.md)|Indique le contrôle de redessiner.|  
|[CMFCPreviewCtrlImpl::SetDocument](../Topic/CMFCPreviewCtrlImpl::SetDocument.md)|Appelé par le gestionnaire d'aperçu pour créer une relation entre l'implémentation de document et le contrôle d'aperçu.|  
|[CMFCPreviewCtrlImpl::SetHost](../Topic/CMFCPreviewCtrlImpl::SetHost.md)|Définit un nouveau parent pour ce contrôle.|  
|[CMFCPreviewCtrlImpl::SetPreviewVisuals](../Topic/CMFCPreviewCtrlImpl::SetPreviewVisuals.md)|Appelé par un gestionnaire riche d'aperçu lorsqu'il doit définir des visuels de contenu d'aperçu riche.|  
|[CMFCPreviewCtrlImpl::SetRect](../Topic/CMFCPreviewCtrlImpl::SetRect.md)|Définit un nouveau rectangle englobant de ce contrôle.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCPreviewCtrlImpl::DoPaint](../Topic/CMFCPreviewCtrlImpl::DoPaint.md)|Appelé par l'infrastructure pour afficher l'aperçu.|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCPreviewCtrlImpl::m\_clrBackColor](../Topic/CMFCPreviewCtrlImpl::m_clrBackColor.md)|Couleur d'arrière\-plan de la fenêtre d'aperçu.|  
|[CMFCPreviewCtrlImpl::m\_clrTextColor](../Topic/CMFCPreviewCtrlImpl::m_clrTextColor.md)|Couleur de texte de la fenêtre d'aperçu.|  
|[CMFCPreviewCtrlImpl::m\_font](../Topic/CMFCPreviewCtrlImpl::m_font.md)|La police du texte dans la fenêtre d'aperçu.|  
|[CMFCPreviewCtrlImpl::m\_pDocument](../Topic/CMFCPreviewCtrlImpl::m_pDocument.md)|Un pointeur vers un document dont le contenu est affiché un aperçu de dans le contrôle.|  
  
## Notes  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCPreviewCtrlImpl](../../mfc/reference/cmfcpreviewctrlimpl-class.md)  
  
## Configuration requise  
 **En\-tête :** afxwin.h