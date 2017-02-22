---
title: "CComApartment Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CComApartment"
  - "CComApartment"
  - "ATL.CComApartment"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "apartments in ATL EXE modules"
  - "CComApartment class"
ms.assetid: dbc177d7-7ee4-45f2-b563-d578a467ca93
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CComApartment Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit la prise en charge de gérer un " apartment " dans un module regroupé par thread EXE.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
class CComApartment  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComApartment::CComApartment](../Topic/CComApartment::CComApartment.md)|Constructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComApartment::Apartment](../Topic/CComApartment::Apartment.md)|Marque l'adresse de départ du thread.|  
|[CComApartment::GetLockCount](../Topic/CComApartment::GetLockCount.md)|Retourne le nombre de verrous actuel du thread.|  
|[CComApartment::Lock](../Topic/CComApartment::Lock.md)|Incrémente le nombre de verrous du thread.|  
|[CComApartment::Unlock](../Topic/CComApartment::Unlock.md)|Décrémente le nombre de verrous du thread.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComApartment::m\_dwThreadID](../Topic/CComApartment::m_dwThreadID.md)|Contient l'identificateur du thread.|  
|[CComApartment::m\_hThread](../Topic/CComApartment::m_hThread.md)|Contient le handle du thread.|  
|[CComApartment::m\_nLockCnt](../Topic/CComApartment::m_nLockCnt.md)|Contient le nombre de verrous actuel du thread.|  
  
## Notes  
 `CComApartment` est utilisé par [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) pour gérer un " apartment " dans un module regroupé par thread EXE.  `CComApartment` fournit des méthodes pour incrémenter ou décrémenter le nombre de verrous sur un thread.  
  
## Configuration requise  
 **Header:** atlbase.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)