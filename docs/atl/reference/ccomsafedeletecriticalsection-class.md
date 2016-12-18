---
title: "CComSafeDeleteCriticalSection Class | Microsoft Docs"
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
  - "CComSafeDeleteCriticalSection"
  - "ATL::CComSafeDeleteCriticalSection"
  - "ATL.CComSafeDeleteCriticalSection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComSafeDeleteCriticalSection class"
ms.assetid: 4d2932c4-ba8f-48ec-8664-1db8bed01314
caps.latest.revision: 18
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComSafeDeleteCriticalSection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes pour obtenir et libérer la propriété d'un objet de section critique.  
  
## Syntaxe  
  
```  
  
class CComSafeDeleteCriticalSection : public CComCriticalSection  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection](../Topic/CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection.md)|Constructeur.|  
|[CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection](../Topic/CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComSafeDeleteCriticalSection::Init](../Topic/CComSafeDeleteCriticalSection::Init.md)|Crée et initialise un objet de section critique.|  
|[CComSafeDeleteCriticalSection::Lock](../Topic/CComSafeDeleteCriticalSection::Lock.md)|Obtient la propriété de l'objet de section critique.|  
|[CComSafeDeleteCriticalSection::Term](../Topic/CComSafeDeleteCriticalSection::Term.md)|Libère des ressources système utilisées par l'objet de section critique.|  
  
### Membres de données  
  
|||  
|-|-|  
|[m\_bInitialized](../Topic/CComSafeDeleteCriticalSection::m_bInitialized.md)|Diminue si l'objet interne de **CRITICAL\_SECTION** a été initialisé.|  
  
## Notes  
 `CComSafeDeleteCriticalSection` dérive de la classe [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md).  Toutefois, `CComSafeDeleteCriticalSection` fournit des mécanismes de sécurité supplémentaires sur [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md).  
  
 Lorsqu'une instance d' `CComSafeDeleteCriticalSection` hors de portée ou est explicitement supprimé de la mémoire, l'objet de section critique sous\-jacent est automatiquement nettoyé s'il est encore valide.  En outre, la méthode de [CComSafeDeleteCriticalSection::Term](../Topic/CComSafeDeleteCriticalSection::Term.md) quittera correctement si l'objet de section critique sous\-jacent n'a pas encore été alloué ou a déjà été récupéré de la mémoire.  
  
 Consultez [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) pour plus d'informations sur les classes d'assistance de section critique.  
  
## Hiérarchie d'héritage  
 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)  
  
 `CComSafeDeleteCriticalSection`  
  
## Configuration requise  
 **Header:** atlcore.h  
  
## Voir aussi  
 [CComCriticalSection Class](../../atl/reference/ccomcriticalsection-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)