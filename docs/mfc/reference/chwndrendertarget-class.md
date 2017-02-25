---
title: "CHwndRenderTarget Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CHwndRenderTarget"
  - "afxrendertarget/CHwndRenderTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHwndRenderTarget (classe)"
ms.assetid: aa65b69f-7202-46ea-af81-ef325da0b840
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# CHwndRenderTarget Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wrapper pour ID2D1HwndRenderTarget.  
  
## Syntaxe  
  
```  
class CHwndRenderTarget : public CRenderTarget;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CHwndRenderTarget::CHwndRenderTarget](../Topic/CHwndRenderTarget::CHwndRenderTarget.md)|Construit un objet CHwndRenderTarget à partir de l'objet HWND.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CHwndRenderTarget::Attach](../Topic/CHwndRenderTarget::Attach.md)|Attache l'interface de la cible de rendu existante à l'objet|  
|[CHwndRenderTarget::CheckWindowState](../Topic/CHwndRenderTarget::CheckWindowState.md)|Indique si l'objet HWND associé à cette cible de rendu est occluse.|  
|[CHwndRenderTarget::Create](../Topic/CHwndRenderTarget::Create.md)|Crée une cible de rendu associée à la fenêtre|  
|[CHwndRenderTarget::Detach](../Topic/CHwndRenderTarget::Detach.md)|Détache l'interface de la cible de rendu de l'objet|  
|[CHwndRenderTarget::GetHwnd](../Topic/CHwndRenderTarget::GetHwnd.md)|Retourne l'objet HWND associé à cette cible de rendu.|  
|[CHwndRenderTarget::GetHwndRenderTarget](../Topic/CHwndRenderTarget::GetHwndRenderTarget.md)|Renvoie l'interface ID2D1HwndRenderTarget.|  
|[CHwndRenderTarget::ReCreate](../Topic/CHwndRenderTarget::ReCreate.md)|Crée de nouveau une cible de rendu associée à la fenêtre|  
|[CHwndRenderTarget::Resize](../Topic/CHwndRenderTarget::Resize.md)|Remplace la taille de la cible de rendu par la taille en pixels spécifiée|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CHwndRenderTarget::operator ID2D1HwndRenderTarget\*](../Topic/CHwndRenderTarget::operator%20ID2D1HwndRenderTarget*.md)|Renvoie l'interface ID2D1HwndRenderTarget.|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CHwndRenderTarget::m\_pHwndRenderTarget](../Topic/CHwndRenderTarget::m_pHwndRenderTarget.md)|Pointeur vers un objet ID2D1HwndRenderTarget.|  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
 [CHwndRenderTarget](../../mfc/reference/chwndrendertarget-class.md)  
  
## Configuration requise  
 **En\-tête :** afxrendertarget.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)