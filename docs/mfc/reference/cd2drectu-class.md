---
title: "Classe CD2DRectU | Microsoft Docs"
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
  - "CD2DRectU"
  - "afxrendertarget/CD2DRectU"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DRectU (classe)"
ms.assetid: a62f17d1-011d-4867-8f51-fd7e7c00561d
caps.latest.revision: 18
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe CD2DRectU
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wrapper pour `D2D1_RECT_U`.  
  
## Syntaxe  
  
```  
class CD2DRectU : public D2D1_RECT_U;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DRectU::CD2DRectU](../Topic/CD2DRectU::CD2DRectU.md)|Surchargé.  Construit un objet d' `CD2DRectU` d'objet d' `D2D1_RECT_U` .|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DRectU::IsNull](../Topic/CD2DRectU::IsNull.md)|Retourne une valeur d' `boolean` qui indique si une expression ne contient pas de données valide \(`null`\).|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DRectU::operator CRect](../Topic/CD2DRectU::operator%20CRect.md)|Convertit `CD2DRectU` à l'objet d' `CRect` .|  
  
## Hiérarchie d'héritage  
 `D2D1_RECT_U`  
  
 [CD2DRectU](../../mfc/reference/cd2drectu-class.md)  
  
## Configuration requise  
 **En\-tête :** afxrendertarget.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)