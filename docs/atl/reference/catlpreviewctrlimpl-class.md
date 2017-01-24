---
title: "CAtlPreviewCtrlImpl Class | Microsoft Docs"
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
  - "atlpreviewctrlimpl/ATL::CAtlPreviewCtrlImpl"
  - "CAtlPreviewCtrlImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlPreviewCtrlImpl class"
ms.assetid: 39b3299e-07e4-4abc-9b6e-b54bfa3b0802
caps.latest.revision: 26
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlPreviewCtrlImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe est une implémentation ATL d'une fenêtre définie sur une fenêtre hôte donné par le shell pour l'aperçu riche.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
class CAtlPreviewCtrlImpl : public CWindowImpl<CAtlPreviewCtrlImpl>, public IPreviewCtrl;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlPreviewCtrlImpl::~CAtlPreviewCtrlImpl](../Topic/CAtlPreviewCtrlImpl::~CAtlPreviewCtrlImpl.md)|Détruit un objet contrôle d'aperçu.|  
|[CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl](../Topic/CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl.md)|Construit un objet contrôle d'aperçu.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlPreviewCtrlImpl::Create](../Topic/CAtlPreviewCtrlImpl::Create.md)|Appelé par un gestionnaire riche d'aperçu pour créer la fenêtre de windows.|  
|[CAtlPreviewCtrlImpl::Destroy](../Topic/CAtlPreviewCtrlImpl::Destroy.md)|Appelé par un gestionnaire riche d'aperçu lorsqu'il doit détruire ce contrôle.|  
|[CAtlPreviewCtrlImpl::Focus](../Topic/CAtlPreviewCtrlImpl::Focus.md)|Définit le focus d'entrée sur ce contrôle.|  
|[CAtlPreviewCtrlImpl::OnPaint](../Topic/CAtlPreviewCtrlImpl::OnPaint.md)|Gère le message de WM\_PAINT.|  
|[CAtlPreviewCtrlImpl::Redraw](../Topic/CAtlPreviewCtrlImpl::Redraw.md)|Indique le contrôle de redessiner.|  
|[CAtlPreviewCtrlImpl::SetHost](../Topic/CAtlPreviewCtrlImpl::SetHost.md)|Définit un nouveau parent pour ce contrôle.|  
|[CAtlPreviewCtrlImpl::SetPreviewVisuals](../Topic/CAtlPreviewCtrlImpl::SetPreviewVisuals.md)|Appelé par un gestionnaire riche d'aperçu lorsqu'il doit définir des visuels de contenu d'aperçu riche.|  
|[CAtlPreviewCtrlImpl::SetRect](../Topic/CAtlPreviewCtrlImpl::SetRect.md)|Définit un nouveau rectangle englobant de ce contrôle.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlPreviewCtrlImpl::DoPaint](../Topic/CAtlPreviewCtrlImpl::DoPaint.md)|Appelé par l'infrastructure pour afficher l'aperçu.|  
  
### Constantes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlPreviewCtrlImpl::m\_plf](../Topic/CAtlPreviewCtrlImpl::m_plf.md)|La police du texte dans la fenêtre d'aperçu.|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlPreviewCtrlImpl::m\_clrBack](../Topic/CAtlPreviewCtrlImpl::m_clrBack.md)|Couleur d'arrière\-plan de la fenêtre d'aperçu.|  
|[CAtlPreviewCtrlImpl::m\_clrText](../Topic/CAtlPreviewCtrlImpl::m_clrText.md)|Couleur de texte de la fenêtre d'aperçu.|  
  
## Notes  
  
## Hiérarchie d'héritage  
 `TBase`  
  
 `ATL::CMessageMap`  
  
 `ATL::CWindowImplRoot<TBase>`  
  
 `ATL::CWindowImplBaseT<TBase,TWinTraits>`  
  
 [ATL::CWindowImpl\<CAtlPreviewCtrlImpl\>](../../atl/reference/cwindowimpl-class.md)  
  
 `IPreviewCtrl`  
  
 `ATL::CAtlPreviewCtrlImpl`  
  
## Configuration requise  
 **Header:** atlpreviewctrlimpl.h  
  
## Voir aussi  
 [ATL COM Desktop Components](../../atl/atl-com-desktop-components.md)