---
title: "CHandle Class | Microsoft Docs"
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
  - "ATL.CHandle"
  - "ATL::CHandle"
  - "CHandle"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHandle class"
ms.assetid: 883e9db5-40ec-4e29-9c74-4dd2ddd2e35d
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CHandle Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes pour la création et l'utilisation d'un objet de handle.  
  
## Syntaxe  
  
```  
  
class CHandle  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CHandle::CHandle](../Topic/CHandle::CHandle.md)|Constructeur.|  
|[CHandle::~CHandle](../Topic/CHandle::~CHandle.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CHandle::Attach](../Topic/CHandle::Attach.md)|Appelez cette méthode pour lier l'objet d' `CHandle` à un handle existant.|  
|[CHandle::Close](../Topic/CHandle::Close.md)|Appelez cette méthode pour fermer un objet d' `CHandle` .|  
|[CHandle::Detach](../Topic/CHandle::Detach.md)|Appelez cette méthode pour détacher un handle d'un objet d' `CHandle` .|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CHandle::operator HANDLE](../Topic/CHandle::operator%20HANDLE.md)|Retourne la valeur du handle stocké.|  
|[CHandle::operator \=](../Topic/CHandle::operator%20=.md)|Opérateur d'assignation|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CHandle::m\_h](../Topic/CHandle::m_h.md)|La variable membre qui stocke le handle.|  
  
## Notes  
 Un objet d' `CHandle` peut être utilisée chaque fois qu'un handle est requis : la principale différence est que l'objet d' `CHandle` sera automatiquement supprimé.  
  
> [!NOTE]
>  Certaines fonctions d'API utiliseront NULL comme handle vide ou non valide, tandis que d'autres utilisent INVALID\_HANDLE\_VALUE.  Les utilisations d'`CHandle` uniquement ANNULENT et traiteront INVALID\_HANDLE\_VALUE comme vraie handle.  Si vous appelez une API qui peut retourner INVALID\_HANDLE\_VALUE, vous devez vérifier cette valeur avant d'appeler [CHandle::Attach](../Topic/CHandle::Attach.md) ou le passer au constructeur d' `CHandle` , puis passez à la place NULL.  
  
## Configuration requise  
 **Header:** atlbase.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)