---
title: "CAtlModule Class | Microsoft Docs"
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
  - "ATL::CAtlModule"
  - "CAtlModule"
  - "ATL.CAtlModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlModule class"
ms.assetid: 63fe02f1-4c4b-4e7c-ae97-7ad7b4252415
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlModule Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes utilisées par plusieurs classes de module ATL.  
  
## Syntaxe  
  
```  
  
   class ATL_NO_VTABLE CAtlModule :  
public _ATL_MODULE  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlModule::CAtlModule](../Topic/CAtlModule::CAtlModule.md)|Constructeur.|  
|[CAtlModule::~CAtlModule](../Topic/CAtlModule::~CAtlModule.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlModule::AddCommonRGSReplacements](../Topic/CAtlModule::AddCommonRGSReplacements.md)|Substituez cette méthode pour ajouter des paramètres à la table de remplacement de composant de Registre ATL \(registre\).|  
|[CAtlModule::AddTermFunc](../Topic/CAtlModule::AddTermFunc.md)|Ajoute une nouvelle fonction à appeler lorsque le package se termine.|  
|[CAtlModule::GetGITPtr](../Topic/CAtlModule::GetGITPtr.md)|Retourne le pointeur d'interface globale.|  
|[CAtlModule::GetLockCount](../Topic/CAtlModule::GetLockCount.md)|Retourne le nombre de verrous.|  
|[CAtlModule::Lock](../Topic/CAtlModule::Lock.md)|Incrémente le nombre de verrous.|  
|[CAtlModule::Term](../Topic/CAtlModule::Term.md)|Libère toutes les données membres.|  
|[CAtlModule::Unlock](../Topic/CAtlModule::Unlock.md)|Décrémente le nombre de verrous.|  
|[CAtlModule::UpdateRegistryFromResourceD](../Topic/CAtlModule::UpdateRegistryFromResourceD.md)|Exécute le script contenu dans une ressource spécifiée pour inscrire ou annuler l'inscription d'un objet.|  
|[CAtlModule::UpdateRegistryFromResourceDHelper](../Topic/CAtlModule::UpdateRegistryFromResourceDHelper.md)|Cette méthode est appelée par `UpdateRegistryFromResourceD` pour effectuer la mise à jour de Registre.|  
|[CAtlModule::UpdateRegistryFromResourceS](../Topic/CAtlModule::UpdateRegistryFromResourceS.md)|Exécute le script contenu dans une ressource spécifiée pour inscrire ou annuler l'inscription d'un objet.  Cette méthode lie statiquement au composant de Registre ATL.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlModule::m\_libid](../Topic/CAtlModule::m_libid.md)|Contient le GUID du module en cours.|  
|[CAtlModule::m\_pGIT](../Topic/CAtlModule::m_pGIT.md)|Pointeur vers un Tableau global d'interface.|  
  
## Notes  
 Cette classe est utilisée par [classe de CAtlDllModuleT](../../atl/reference/catldllmodulet-class.md), [classe de CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md), et [classe de CAtlServiceModuleT](../../atl/reference/catlservicemodulet-class.md) pour fournir la prise en charge des applications de DLL, les applications EXE, et les services windows, respectivement.  
  
 Pour plus d'informations sur les modules dans ATL, consultez [Classes de module ATL](../../atl/atl-module-classes.md).  
  
 Cette classe substitue [classe de CComModule](../../atl/reference/ccommodule-class.md) obsolète utilisé dans les versions antérieures ATL.  
  
## Hiérarchie d'héritage  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)  
  
 `CAtlModule`  
  
## Configuration requise  
 **Header:** atlbase.h  
  
## Voir aussi  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Module, classes](../../atl/atl-module-classes.md)   
 [Composant de registre \(Inscription\)](../../atl/atl-registry-component-registrar.md)