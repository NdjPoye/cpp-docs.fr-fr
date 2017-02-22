---
title: "Classe CD2DResource | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxrendertarget/CD2DResource"
  - "CD2DResource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DResource (classe)"
ms.assetid: 34e3ee18-aab6-4c39-9294-de869e1f7820
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# Classe CD2DResource
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Classe abstraite qui propose une interface pour créer et gérer des ressources D2D telles que des pinceaux, des couches et des textes.  
  
## Syntaxe  
  
```  
class CD2DResource : public CObject;  
```  
  
## Membres  
  
### Constructeurs protégés  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DResource::CD2DResource](../Topic/CD2DResource::CD2DResource.md)|Construit un objet CD2DResource.|  
|[CD2DResource::~CD2DResource](../Topic/CD2DResource::~CD2DResource.md)|Le destructeur.  Appelé lorsqu'un objet ressource D2D est détruit.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DResource::Create](../Topic/CD2DResource::Create.md)|Crée CD2DResource.|  
|[CD2DResource::Destroy](../Topic/CD2DResource::Destroy.md)|Détruit un objet CD2DResource.|  
|[CD2DResource::IsValid](../Topic/CD2DResource::IsValid.md)|Vérifie la validité des ressources|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DResource::IsAutoDestroy](../Topic/CD2DResource::IsAutoDestroy.md)|Vérifiez l'indicateur de destruction automatique.|  
|[CD2DResource::ReCreate](../Topic/CD2DResource::ReCreate.md)|Crée de nouveau un objet CD2DResource.|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DResource::m\_bIsAutoDestroy](../Topic/CD2DResource::m_bIsAutoDestroy.md)|La ressource sera détruite par le propriétaire \(CRenderTarget\)|  
|[CD2DResource::m\_pParentTarget](../Topic/CD2DResource::m_pParentTarget.md)|Pointeur au parent CRenderTarget|  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
## Configuration requise  
 **En\-tête :** afxrendertarget.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)