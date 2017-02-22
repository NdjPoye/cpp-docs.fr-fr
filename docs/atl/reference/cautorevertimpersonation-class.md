---
title: "CAutoRevertImpersonation Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CAutoRevertImpersonation"
  - "CAutoRevertImpersonation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAutoRevertImpersonation class"
ms.assetid: 43732849-1940-4bd4-9d52-7a5698bb8838
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CAutoRevertImpersonation Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe retourne des objets de [CAccessToken](../../atl/reference/caccesstoken-class.md) un état nonimpersonating lorsqu'elle est hors de portée.  
  
## Syntaxe  
  
```  
  
class CAutoRevertImpersonation  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAutoRevertImpersonation::CAutoRevertImpersonation](../Topic/CAutoRevertImpersonation::CAutoRevertImpersonation.md)|Construit un objet d' `CAutoRevertImpersonation`|  
|[CAutoRevertImpersonation::~CAutoRevertImpersonation](../Topic/CAutoRevertImpersonation::~CAutoRevertImpersonation.md)|Détruit l'objet et retourne l'emprunt d'identité de jeton d'accès.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAutoRevertImpersonation::Attach](../Topic/CAutoRevertImpersonation::Attach.md)|Automatise le retour d'emprunt d'identité d'un jeton d'accès.|  
|[CAutoRevertImpersonation::Detach](../Topic/CAutoRevertImpersonation::Detach.md)|Annule le retour automatique d'emprunt d'identité.|  
|[CAutoRevertImpersonation::GetAccessToken](../Topic/CAutoRevertImpersonation::GetAccessToken.md)|Récupère le actuel de jeton d'accès associé à cet objet.|  
  
## Notes  
 [jeton d'accès](http://msdn.microsoft.com/library/windows/desktop/aa374909) est un objet qui décrit le contexte de sécurité d'un processus ou un thread et est alloué à chaque utilisateur stocké sur Windows NT ou un système Windows 2000.  Ces jetons d'accès peuvent être représentés avec la classe d' `CAccessToken` .  
  
 Il est parfois nécessaire d'emprunter les jetons d'accès.  Cette classe est fournie plus pratique, mais il n'exécute pas l'emprunt d'identité des jetons d'accès ; il effectue uniquement le retour automatique à un état nonimpersonated.  C'est parce que l'emprunt d'identité jeton d'accès peut être exécuté plusieurs façons.  
  
 Pour une introduction au modèle de contrôle d'accès dans windows, consultez [contrôle d'accès](http://msdn.microsoft.com/library/windows/desktop/aa374860) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Configuration requise  
 **Header:** atlsecurity.h  
  
## Voir aussi  
 [Exemple ATLSecurity](../../top/visual-cpp-samples.md)   
 [Access Tokens](http://msdn.microsoft.com/library/windows/desktop/aa374909)   
 [Class Overview](../../atl/atl-class-overview.md)