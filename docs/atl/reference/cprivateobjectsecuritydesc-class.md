---
title: "CPrivateObjectSecurityDesc Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CPrivateObjectSecurityDesc"
  - "ATL::CPrivateObjectSecurityDesc"
  - "CPrivateObjectSecurityDesc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPrivateObjectSecurityDesc class"
ms.assetid: 2c4bbb13-bf99-4833-912a-197f6815bb5d
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPrivateObjectSecurityDesc Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe représente un objet privé modèle de sécurité des objets.  
  
## Syntaxe  
  
```  
  
class CPrivateObjectSecurityDesc : public CSecurityDesc  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc](../Topic/CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc.md)|Constructeur.|  
|[CPrivateObjectSecurityDesc::~CPrivateObjectSecurityDesc](../Topic/CPrivateObjectSecurityDesc::~CPrivateObjectSecurityDesc.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CPrivateObjectSecurityDesc::ConvertToAutoInherit](../Topic/CPrivateObjectSecurityDesc::ConvertToAutoInherit.md)|Appelez cette méthode pour convertir un modèle et ses listes de contrôle d'accès \(ACLs\) de sécurité dans un format qui prend en charge la propagation automatique des ACEs pouvant être hérité \(ACEs\).|  
|[CPrivateObjectSecurityDesc::Create](../Topic/CPrivateObjectSecurityDesc::Create.md)|Appelez cette méthode pour allouer et initialiser un modèle auto\-relatif de sécurité pour l'objet privé créé par le gestionnaire des ressources appelant.|  
|[CPrivateObjectSecurityDesc::Get](../Topic/CPrivateObjectSecurityDesc::Get.md)|Appelez cette méthode pour récupérer les informations du modèle privé de la sécurité d'un objet.|  
|[CPrivateObjectSecurityDesc::Set](../Topic/CPrivateObjectSecurityDesc::Set.md)|Appelez cette méthode pour modifier le modèle privé de la sécurité d'un objet.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[opérateur \=](../Topic/CPrivateObjectSecurityDesc::operator%20=.md)|Opérateur d'assignation|  
  
## Notes  
 Cette classe, dérivée de [CSecurityDesc](../../atl/reference/csecuritydesc-class.md), fournit des méthodes pour créer et gérer le modèle de sécurité d'un objet privé.  
  
 Pour une introduction au modèle de contrôle d'accès dans windows, consultez [contrôle d'accès](http://msdn.microsoft.com/library/windows/desktop/aa374860) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Hiérarchie d'héritage  
 [CSecurityDesc](../../atl/reference/csecuritydesc-class.md)  
  
 `CPrivateObjectSecurityDesc`  
  
## Configuration requise  
 **Header:** atlsecurity.h  
  
## Voir aussi  
 [SECURITY\_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Security Global Functions](../../atl/reference/security-global-functions.md)   
 [CSecurityDesc Class](../../atl/reference/csecuritydesc-class.md)