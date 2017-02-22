---
title: "CAtlBaseModule Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CAtlBaseModule"
  - "ATL.CAtlBaseModule"
  - "CAtlBaseModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlBaseModule class"
ms.assetid: 55ade80c-9b0c-4c51-933e-2158436c1096
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CAtlBaseModule Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe est instanciée dans chaque projet ATL.  
  
## Syntaxe  
  
```  
  
   class CAtlBaseModule :  
public _ATL_BASE_MODULE  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlBaseModule::CAtlBaseModule](../Topic/CAtlBaseModule::CAtlBaseModule.md)|Constructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlBaseModule::AddResourceInstance](../Topic/CAtlBaseModule::AddResourceInstance.md)|Ajoute une instance de ressources à la liste des handles stockés.|  
|[CAtlBaseModule::GetHInstanceAt](../Topic/CAtlBaseModule::GetHInstanceAt.md)|Retourne un handle à une instance spécifique de ressources.|  
|[CAtlBaseModule::GetModuleInstance](../Topic/CAtlBaseModule::GetModuleInstance.md)|Retourne l'instance du module d'un objet d' `CAtlBaseModule` .|  
|[CAtlBaseModule::GetResourceInstance](../Topic/CAtlBaseModule::GetResourceInstance.md)|Retourne l'instance de ressource d'un objet d' `CAtlBaseModule` .|  
|[CAtlBaseModule::RemoveResourceInstance](../Topic/CAtlBaseModule::RemoveResourceInstance.md)|Supprime une instance de ressource dans la liste des handles stockés.|  
|[CAtlBaseModule::SetResourceInstance](../Topic/CAtlBaseModule::SetResourceInstance.md)|Définit l'instance de ressource d'un objet d' `CAtlBaseModule` .|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlBaseModule::m\_bInitFailed](../Topic/CAtlBaseModule::m_bInitFailed.md)|Une variable qui indique si l'initialisation de module a échoué.|  
  
## Notes  
 Une instance d' `CAtlBaseModule` nommé le \_AtlBaseModule est présente dans chaque projet ATL, contenant un handle vers l'instance du package, un handle au module qui contient les ressources \(que par défaut, sont autorisés et le même\), et un tableau de handles aux modules fournissant les ressources primaire.  `CAtlBaseModule` peut être toute sécurité accessible à partir de plusieurs threads.  
  
 Cette classe substitue la classe obsolète de [CComModule](../../atl/reference/ccommodule-class.md) utilisée dans les versions antérieures ATL.  
  
## Hiérarchie d'héritage  
 [\_ATL\_BASE\_MODULE](../Topic/_ATL_BASE_MODULE.md)  
  
 `CAtlBaseModule`  
  
## Configuration requise  
 **Header:** atlcore.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)   
 [Module, classes](../../atl/atl-module-classes.md)