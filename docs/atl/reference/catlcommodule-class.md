---
title: "CAtlComModule Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CAtlComModule"
  - "CAtlComModule"
  - "ATL::CAtlComModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlComModule class"
ms.assetid: af5dd71a-a0d1-4a2e-9a24-154a03381c75
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CAtlComModule Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente un module de serveur COM.  
  
## Syntaxe  
  
```  
  
   class CAtlComModule :  
public _ATL_COM_MODULE  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlComModule::CAtlComModule](../Topic/CAtlComModule::CAtlComModule.md)|Constructeur.|  
|[CAtlComModule::~CAtlComModule](../Topic/CAtlComModule::~CAtlComModule.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlComModule::RegisterServer](../Topic/CAtlComModule::RegisterServer.md)|Appelez cette méthode pour mettre à jour la base de registres pour chaque objet dans la table d'objets.|  
|[CAtlComModule::RegisterTypeLib](../Topic/CAtlComModule::RegisterTypeLib.md)|Appelez cette méthode pour enregistrer une bibliothèque de types.|  
|[CAtlComModule::UnregisterServer](../Topic/CAtlComModule::UnregisterServer.md)|Appelez cette méthode pour annuler l'enregistrement chaque objet dans la table d'objets.|  
|[CAtlComModule::UnRegisterTypeLib](../Topic/CAtlComModule::UnRegisterTypeLib.md)|Appelez cette méthode pour annuler l'enregistrement une bibliothèque de types.|  
  
## Notes  
 `CAtlComModule` implémente un module de serveur COM, ce qui permet à un client d'accéder aux composants du module.  
  
 Cette classe substitue la classe obsolète de [CComModule](../../atl/reference/ccommodule-class.md) utilisée dans les versions antérieures ATL.  Consultez [Classes de module ATL](../../atl/atl-module-classes.md) pour plus de détails.  
  
## Hiérarchie d'héritage  
 [\_ATL\_COM\_MODULE](../Topic/_ATL_COM_MODULE.md)  
  
 `CAtlComModule`  
  
## Configuration requise  
 **Header:** atlbase.h  
  
## Voir aussi  
 [\_ATL\_COM\_MODULE](../Topic/_ATL_COM_MODULE.md)   
 [Class Overview](../../atl/atl-class-overview.md)