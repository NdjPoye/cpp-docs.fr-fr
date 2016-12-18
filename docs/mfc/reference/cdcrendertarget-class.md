---
title: "Classe CDCRenderTarget | Microsoft Docs"
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
  - "afxrendertarget/CDCRenderTarget"
  - "CDCRenderTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDCRenderTarget (classe)"
ms.assetid: aa8059c9-08e6-49e4-9b8c-00fa54077a61
caps.latest.revision: 16
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe CDCRenderTarget
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wrapper pour ID2D1DCRenderTarget.  
  
## Syntaxe  
  
```  
class CDCRenderTarget : public CRenderTarget;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CDCRenderTarget::CDCRenderTarget](../Topic/CDCRenderTarget::CDCRenderTarget.md)|Construit un objet CDCRenderTarget.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDCRenderTarget::Attach](../Topic/CDCRenderTarget::Attach.md)|Attache l'interface de la cible de rendu existante à l'objet|  
|[CDCRenderTarget::BindDC](../Topic/CDCRenderTarget::BindDC.md)|Lie la cible de rendu au contexte du périphérique pour lequel il lance des commandes de dessin|  
|[CDCRenderTarget::Create](../Topic/CDCRenderTarget::Create.md)|Crée CDCRenderTarget.|  
|[CDCRenderTarget::Detach](../Topic/CDCRenderTarget::Detach.md)|Détache l'interface de la cible de rendu de l'objet|  
|[CDCRenderTarget::GetDCRenderTarget](../Topic/CDCRenderTarget::GetDCRenderTarget.md)|Renvoie l'interface ID2D1DCRenderTarget|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CDCRenderTarget::operator ID2D1DCRenderTarget\*](../Topic/CDCRenderTarget::operator%20ID2D1DCRenderTarget*.md)|Renvoie l'interface ID2D1DCRenderTarget|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CDCRenderTarget::m\_pDCRenderTarget](../Topic/CDCRenderTarget::m_pDCRenderTarget.md)|Pointeur vers un objet ID2D1DCRenderTarget.|  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
 [CDCRenderTarget](../../mfc/reference/cdcrendertarget-class.md)  
  
## Configuration requise  
 **En\-tête :** afxrendertarget.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)