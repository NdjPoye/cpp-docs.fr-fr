---
title: "CSecurityDesc Class | Microsoft Docs"
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
  - "ATL::CSecurityDesc"
  - "ATL.CSecurityDesc"
  - "CSecurityDesc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSecurityDesc class"
ms.assetid: 3767a327-378f-4690-ba40-4d9f6a1f5ee4
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSecurityDesc Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe est un wrapper pour la structure de **SECURITY\_DESCRIPTOR** .  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
class CSecurityDesc  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSecurityDesc::CSecurityDesc](../Topic/CSecurityDesc::CSecurityDesc.md)|Constructeur.|  
|[CSecurityDesc::~CSecurityDesc](../Topic/CSecurityDesc::~CSecurityDesc.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CSecurityDesc::FromString](../Topic/CSecurityDesc::FromString.md)|Convertit un descripteur de sécurité de format de chaîne dans un modèle valide et fonctionnel de sécurité.|  
|[CSecurityDesc::GetControl](../Topic/CSecurityDesc::GetControl.md)|Récupère les paramètres du modèle de sécurité.|  
|[CSecurityDesc::GetDacl](../Topic/CSecurityDesc::GetDacl.md)|Extrait les informations de discrétionnaires \(DACL\) de liste de contrôle d'accès du modèle de sécurité.|  
|[CSecurityDesc::GetGroup](../Topic/CSecurityDesc::GetGroup.md)|Extrait les informations de groupe principal du modèle de sécurité.|  
|[CSecurityDesc::GetOwner](../Topic/CSecurityDesc::GetOwner.md)|Récupère l'informaton propriétaire du modèle de sécurité.|  
|[CSecurityDesc::GetPSECURITY\_DESCRIPTOR](../Topic/CSecurityDesc::GetPSECURITY_DESCRIPTOR.md)|Retourne un pointeur vers une structure de **SECURITY\_DESCRIPTOR** .|  
|[CSecurityDesc::GetSacl](../Topic/CSecurityDesc::GetSacl.md)|Extrait les informations de \(SACL\) de liste de contrôle d'accès système du modèle de sécurité.|  
|[CSecurityDesc::IsDaclAutoInherited](../Topic/CSecurityDesc::IsDaclAutoInherited.md)|Détermine si la liste DACL nulle est configuré pour prendre en charge la propagation automatique.|  
|[CSecurityDesc::IsDaclDefaulted](../Topic/CSecurityDesc::IsDaclDefaulted.md)|Détermine si le modèle de sécurité est configuré avec une valeur par défaut liste DACL nulle.|  
|[CSecurityDesc::IsDaclPresent](../Topic/CSecurityDesc::IsDaclPresent.md)|Détermine si le modèle de sécurité contient une liste DACL.|  
|[CSecurityDesc::IsDaclProtected](../Topic/CSecurityDesc::IsDaclProtected.md)|Détermine si la liste DACL nulle est configuré pour empêcher les modifications.|  
|[CSecurityDesc::IsGroupDefaulted](../Topic/CSecurityDesc::IsGroupDefaulted.md)|Détermine si l'identificateur de sécurité de groupe \(SID\) du modèle de sécurité a été défini par défaut.|  
|[CSecurityDesc::IsOwnerDefaulted](../Topic/CSecurityDesc::IsOwnerDefaulted.md)|Détermine si le propriétaire SID du modèle de sécurité a été défini par défaut.|  
|[CSecurityDesc::IsSaclAutoInherited](../Topic/CSecurityDesc::IsSaclAutoInherited.md)|Détermine si SACL est configuré pour prendre en charge la propagation automatique.|  
|[CSecurityDesc::IsSaclDefaulted](../Topic/CSecurityDesc::IsSaclDefaulted.md)|Détermine si le modèle de sécurité est configuré avec SACL par défaut.|  
|[CSecurityDesc::IsSaclPresent](../Topic/CSecurityDesc::IsSaclPresent.md)|Détermine si le modèle de sécurité contient SACL.|  
|[CSecurityDesc::IsSaclProtected](../Topic/CSecurityDesc::IsSaclProtected.md)|Détermine si SACL est configuré pour empêcher les modifications.|  
|[CSecurityDesc::IsSelfRelative](../Topic/CSecurityDesc::IsSelfRelative.md)|Détermine si le modèle de sécurité est au format auto\-relatif.|  
|[CSecurityDesc::MakeAbsolute](../Topic/CSecurityDesc::MakeAbsolute.md)|Appelez cette méthode pour convertir le modèle de sécurité au format absolu.|  
|[CSecurityDesc::MakeSelfRelative](../Topic/CSecurityDesc::MakeSelfRelative.md)|Appelez cette méthode pour convertir le modèle de sécurité au format auto\-relatif.|  
|[CSecurityDesc::SetControl](../Topic/CSecurityDesc::SetControl.md)|Définit les bits de contrôle d'un descripteur de sécurité.|  
|[CSecurityDesc::SetDacl](../Topic/CSecurityDesc::SetDacl.md)|Place des informations dans une liste DACL.  Si une liste DACL figure déjà dans le modèle de sécurité, il est remplacé.|  
|[CSecurityDesc::SetGroup](../Topic/CSecurityDesc::SetGroup.md)|Définit les informations de groupe principal d'un modèle absolu de sécurité de format, en remplaçant tout présence d'informations de groupe principal déjà.|  
|[CSecurityDesc::SetOwner](../Topic/CSecurityDesc::SetOwner.md)|Définit les informations de propriétaire d'un modèle absolu de sécurité de format, en remplaçant tout présence d'informations de propriétaire déjà.|  
|[CSecurityDesc::SetSacl](../Topic/CSecurityDesc::SetSacl.md)|Définit les informations dans SACL.  Si SACL figure déjà dans le modèle de sécurité, il est remplacé.|  
|[CSecurityDesc::ToString](../Topic/CSecurityDesc::ToString.md)|Convertit un modèle de sécurité à un format de chaîne.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSecurityDesc::operator const SECURITY\_DESCRIPTOR \*](../Topic/CSecurityDesc::operator%20const%20SECURITY_DESCRIPTOR%20*.md)|Retourne un pointeur vers une structure de **SECURITY\_DESCRIPTOR** .|  
|[CSecurityDesc::operator \=](../Topic/CSecurityDesc::operator%20=.md)|Opérateur d'assignation|  
  
## Notes  
 La structure de **SECURITY\_DESCRIPTOR** contient les informations de sécurité associées à un objet.  Les applications utilisent cette structure pour définir et interroger le mode de sécurité d'un objet.  Consultez également l' [AtlGetSecurityDescriptor](../Topic/AtlGetSecurityDescriptor.md).  
  
 Les applications ne doivent pas modifier la structure de **SECURITY\_DESCRIPTOR** directement, et à la place doivent utiliser les méthodes de classe fournies.  
  
 Pour une introduction au modèle de contrôle d'accès dans windows, consultez [contrôle d'accès](http://msdn.microsoft.com/library/windows/desktop/aa374860) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Configuration requise  
 **Header:** atlsecurity.h  
  
## Voir aussi  
 [Sécurité, exemple](../../top/visual-cpp-samples.md)   
 [SECURITY\_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Security Global Functions](../../atl/reference/security-global-functions.md)