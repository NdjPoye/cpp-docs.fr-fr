---
title: "Classe CD2DBitmapBrush | Microsoft Docs"
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
  - "CD2DBitmapBrush"
  - "afxrendertarget/CD2DBitmapBrush"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DBitmapBrush (classe)"
ms.assetid: 46ebbe34-66e0-44c8-af1d-d129e851de5e
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe CD2DBitmapBrush
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wrapper pour ID2D1BitmapBrush.  
  
## Syntaxe  
  
```  
class CD2DBitmapBrush : public CD2DBrush;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DBitmapBrush::CD2DBitmapBrush](../Topic/CD2DBitmapBrush::CD2DBitmapBrush.md)|Surchargé.  Construit un objet CD2DBitmapBrush à partir d'un fichier.|  
|[CD2DBitmapBrush::~CD2DBitmapBrush](../Topic/CD2DBitmapBrush::~CD2DBitmapBrush.md)|Le destructeur.  Appelé lorsqu'un objet brush de l'image bitmap D2D est détruit.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DBitmapBrush::Attach](../Topic/CD2DBitmapBrush::Attach.md)|Attache l'interface de la ressource existante à l'objet|  
|[CD2DBitmapBrush::Create](../Topic/CD2DBitmapBrush::Create.md)|Crée CD2DBitmapBrush.  \(Substitue [CD2DResource::Create](../Topic/CD2DResource::Create.md).\)|  
|[CD2DBitmapBrush::Destroy](../Topic/CD2DBitmapBrush::Destroy.md)|Détruit un objet CD2DBitmapBrush.  \(Substitue [CD2DBrush::Destroy](../Topic/CD2DBrush::Destroy.md).\)|  
|[CD2DBitmapBrush::Detach](../Topic/CD2DBitmapBrush::Detach.md)|Détache l'interface de la ressource de l'objet|  
|[CD2DBitmapBrush::Get](../Topic/CD2DBitmapBrush::Get.md)|Renvoie l'interface ID2D1BitmapBrush|  
|[CD2DBitmapBrush::GetBitmap](../Topic/CD2DBitmapBrush::GetBitmap.md)|Obtient la source de l'image bitmap que ce pinceau utilise pour peindre|  
|[CD2DBitmapBrush::GetExtendModeX](../Topic/CD2DBitmapBrush::GetExtendModeX.md)|Obtient la méthode par laquelle le pinceau dispose en mosaïque horizontale les zones qui s'étendent au\-delà de son image bitmap|  
|[CD2DBitmapBrush::GetExtendModeY](../Topic/CD2DBitmapBrush::GetExtendModeY.md)|Obtient la méthode par laquelle le pinceau dispose en mosaïque verticale les zones qui s'étendent au\-delà de son image bitmap|  
|[CD2DBitmapBrush::GetInterpolationMode](../Topic/CD2DBitmapBrush::GetInterpolationMode.md)|Obtient la méthode d'interpolation utilisée lorsque l'image bitmap du pinceau est mise à l'échelle ou pivotée|  
|[CD2DBitmapBrush::SetBitmap](../Topic/CD2DBitmapBrush::SetBitmap.md)|Spécifie la source de l'image bitmap que ce pinceau utilise pour peindre|  
|[CD2DBitmapBrush::SetExtendModeX](../Topic/CD2DBitmapBrush::SetExtendModeX.md)|Spécifie la manière dont le pinceau dispose en mosaïque horizontale les zones qui s'étendent au\-delà de son image bitmap|  
|[CD2DBitmapBrush::SetExtendModeY](../Topic/CD2DBitmapBrush::SetExtendModeY.md)|Spécifie la manière dont le pinceau dispose en mosaïque verticale les zones qui s'étendent au\-delà de son image bitmap|  
|[CD2DBitmapBrush::SetInterpolationMode](../Topic/CD2DBitmapBrush::SetInterpolationMode.md)|Spécifie le mode d'interpolation utilisée lorsque l'image bitmap du pinceau est mise à l'échelle ou pivotée|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DBitmapBrush::CommonInit](../Topic/CD2DBitmapBrush::CommonInit.md)|Initialise l'objet|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DBitmapBrush::operator ID2D1BitmapBrush\*](../Topic/CD2DBitmapBrush::operator%20ID2D1BitmapBrush*.md)|Renvoie l'interface ID2D1BitmapBrush|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DBitmapBrush::m\_pBitmap](../Topic/CD2DBitmapBrush::m_pBitmap.md)|Stocke un pointeur à un objet CD2DBitmap.|  
|[CD2DBitmapBrush::m\_pBitmapBrush](../Topic/CD2DBitmapBrush::m_pBitmapBrush.md)|Stocke un pointeur à un objet ID2D1BitmapBrush.|  
|[CD2DBitmapBrush::m\_pBitmapBrushProperties](../Topic/CD2DBitmapBrush::m_pBitmapBrushProperties.md)|Propriétés du pinceau de la bitmap.|  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 [CD2DBitmapBrush](../../mfc/reference/cd2dbitmapbrush-class.md)  
  
## Configuration requise  
 **En\-tête :** afxrendertarget.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)