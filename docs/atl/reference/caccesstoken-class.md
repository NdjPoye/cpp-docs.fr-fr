---
title: "CAccessToken Class | Microsoft Docs"
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
  - "ATLSECURITY/CAccessToken"
  - "ATL.CAccessToken"
  - "CAccessToken"
  - "ATL::CAccessToken"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAccessToken class"
ms.assetid: bb5c5945-56a5-4083-b442-76573cee83ab
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAccessToken Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe est un wrapper pour un jeton d'accès.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
class CAccessToken  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAccessToken::~CAccessToken](../Topic/CAccessToken::~CAccessToken.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAccessToken::Attach](../Topic/CAccessToken::Attach.md)|Appelez cette méthode pour prendre la propriété du handle fourni de jeton d'accès.|  
|[CAccessToken::CheckTokenMembership](../Topic/CAccessToken::CheckTokenMembership.md)|Appelez cette méthode pour déterminer si un SID spécifié est activé dans l'objet d' `CAccessToken` .|  
|[CAccessToken::CreateImpersonationToken](../Topic/CAccessToken::CreateImpersonationToken.md)|Appelez cette méthode pour créer un jeton d'accès d'emprunt d'identité.|  
|[CAccessToken::CreatePrimaryToken](../Topic/CAccessToken::CreatePrimaryToken.md)|Appelez cette méthode pour créer un jeton principal.|  
|[CAccessToken::CreateProcessAsUser](../Topic/CAccessToken::CreateProcessAsUser.md)|Appelez cette méthode pour créer un processus qui s'exécutent dans le contexte de sécurité de l'utilisateur représenté par l'objet d' `CAccessToken` .|  
|[CAccessToken::CreateRestrictedToken](../Topic/CAccessToken::CreateRestrictedToken.md)|Appelez cette méthode pour créer un, un objet d' `CAccessToken` .|  
|[CAccessToken::Detach](../Topic/CAccessToken::Detach.md)|Appelez cette méthode pour révoquer la propriété du jeton d'accès.|  
|[CAccessToken::DisablePrivilege](../Topic/CAccessToken::DisablePrivilege.md)|Appelez cette méthode pour désactiver un privilège dans l'objet d' `CAccessToken` .|  
|[CAccessToken::DisablePrivileges](../Topic/CAccessToken::DisablePrivileges.md)|Appelez cette méthode pour désactiver un ou plusieurs privilèges dans l'objet d' `CAccessToken` .|  
|[CAccessToken::EnablePrivilege](../Topic/CAccessToken::EnablePrivilege.md)|Appelez cette méthode pour activer un privilège dans l'objet d' `CAccessToken` .|  
|[CAccessToken::EnablePrivileges](../Topic/CAccessToken::EnablePrivileges.md)|Appelez cette méthode pour activer un ou plusieurs privilèges dans l'objet d' `CAccessToken` .|  
|[CAccessToken::GetDefaultDacl](../Topic/CAccessToken::GetDefaultDacl.md)|Appelez cette méthode pour retourner la valeur par défaut DACL de l'objet d' `CAccessToken` .|  
|[CAccessToken::GetEffectiveToken](../Topic/CAccessToken::GetEffectiveToken.md)|Appelez cette méthode pour obtenir l'objet d' `CAccessToken` égal au jeton d'accès en vigueur pour le thread actuel.|  
|[CAccessToken::GetGroups](../Topic/CAccessToken::GetGroups.md)|Appelez cette méthode pour retourner des groupes symboliques de l'objet d' `CAccessToken` .|  
|[CAccessToken::GetHandle](../Topic/CAccessToken::GetHandle.md)|Appelez cette méthode pour récupérer un handle au jeton d'accès.|  
|[CAccessToken::GetImpersonationLevel](../Topic/CAccessToken::GetImpersonationLevel.md)|Appelez cette méthode pour obtenir le niveau d'emprunt d'identité du jeton d'accès.|  
|[CAccessToken::GetLogonSessionId](../Topic/CAccessToken::GetLogonSessionId.md)|Appelez cette méthode pour obtenir l'ID de session de connexion associé à l'objet d' `CAccessToken` .|  
|[CAccessToken::GetLogonSid](../Topic/CAccessToken::GetLogonSid.md)|Appelez cette méthode pour obtenir la connexion SID associé à l'objet d' `CAccessToken` .|  
|[CAccessToken::GetOwner](../Topic/CAccessToken::GetOwner.md)|Appelez cette méthode pour obtenir le propriétaire associé à l'objet d' `CAccessToken` .|  
|[CAccessToken::GetPrimaryGroup](../Topic/CAccessToken::GetPrimaryGroup.md)|Appelez cette méthode pour obtenir le groupe principal associé à l'objet d' `CAccessToken` .|  
|[CAccessToken::GetPrivileges](../Topic/CAccessToken::GetPrivileges.md)|Appelez cette méthode pour obtenir les privilèges associés à l'objet d' `CAccessToken` .|  
|[CAccessToken::GetProcessToken](../Topic/CAccessToken::GetProcessToken.md)|Appelez cette méthode pour initialiser `CAccessToken` avec le jeton d'accès du processus donné.|  
|[CAccessToken::GetProfile](../Topic/CAccessToken::GetProfile.md)|Appelez cette méthode pour obtenir le handle qui pointe vers le profil utilisateur associé à l'objet d' `CAccessToken` .|  
|[CAccessToken::GetSource](../Topic/CAccessToken::GetSource.md)|Appelez cette méthode pour obtenir la source de l'objet d' `CAccessToken` .|  
|[CAccessToken::GetStatistics](../Topic/CAccessToken::GetStatistics.md)|Appelez cette méthode pour obtenir les informations associées à l'objet d' `CAccessToken` .|  
|[CAccessToken::GetTerminalServicesSessionId](../Topic/CAccessToken::GetTerminalServicesSessionId.md)|Appelez cette méthode pour obtenir l'ID de session Terminal services associé à l'objet d' `CAccessToken` .|  
|[CAccessToken::GetThreadToken](../Topic/CAccessToken::GetThreadToken.md)|Appelez cette méthode pour initialiser `CAccessToken` par le marqueur de thread donné.|  
|[CAccessToken::GetTokenId](../Topic/CAccessToken::GetTokenId.md)|Appelez cette méthode pour obtenir l'ID de jeton associé à l'objet d' `CAccessToken` .|  
|[CAccessToken::GetType](../Topic/CAccessToken::GetType.md)|Appelez cette méthode pour obtenir le type de jeton de l'objet d' `CAccessToken` .|  
|[CAccessToken::GetUser](../Topic/CAccessToken::GetUser.md)|Appelez cette méthode pour identifier l'utilisateur associé à l'objet d' `CAccessToken` .|  
|[CAccessToken::HKeyCurrentUser](../Topic/CAccessToken::HKeyCurrentUser.md)|Appelez cette méthode pour obtenir le handle qui pointe vers le profil utilisateur associé à l'objet d' `CAccessToken` .|  
|[CAccessToken::Impersonate](../Topic/CAccessToken::Impersonate.md)|Appelez cette méthode pour assigner un emprunt d'identité `CAccessToken` à un thread.|  
|[CAccessToken::ImpersonateLoggedOnUser](../Topic/CAccessToken::ImpersonateLoggedOnUser.md)|Appelez cette méthode pour permettre au thread appelant pour emprunter le contexte de sécurité d'un utilisateur connecté.|  
|[CAccessToken::IsTokenRestricted](../Topic/CAccessToken::IsTokenRestricted.md)|Appelez cette méthode pour vérifier si l'objet d' `CAccessToken` contient une liste des SID restreints.|  
|[CAccessToken::LoadUserProfile](../Topic/CAccessToken::LoadUserProfile.md)|Appelez cette méthode pour charger le profil utilisateur associé à l'objet d' `CAccessToken` .|  
|[CAccessToken::LogonUser](../Topic/CAccessToken::LogonUser.md)|Appelez cette méthode pour créer une session de connexion de l'utilisateur associé avec les informations d'identification données.|  
|[CAccessToken::OpenCOMClientToken](../Topic/CAccessToken::OpenCOMClientToken.md)|Appelez cette méthode à partir d'un serveur COM gérant un appel d'un client pour initialiser `CAccessToken` avec le jeton d'accès du client COM.|  
|[CAccessToken::OpenNamedPipeClientToken](../Topic/CAccessToken::OpenNamedPipeClientToken.md)|Appelez cette méthode d'un serveur prenant des requêtes sur un canal nommé d'initialiser `CAccessToken` avec le jeton d'accès du client.|  
|[CAccessToken::OpenRPCClientToken](../Topic/CAccessToken::OpenRPCClientToken.md)|Appelez cette méthode d'un serveur gérant un appel d'un client RPC pour initialiser `CAccessToken` avec le jeton d'accès du client.|  
|[CAccessToken::OpenThreadToken](../Topic/CAccessToken::OpenThreadToken.md)|Appelez cette méthode pour définir le niveau d'emprunt d'identité puis pour initialiser `CAccessToken` par le marqueur de thread donné.|  
|[CAccessToken::PrivilegeCheck](../Topic/CAccessToken::PrivilegeCheck.md)|Appelez cette méthode pour déterminer si un jeu spécifié de privilèges sont activés dans l'objet de **CAccessToken** .|  
|[CAccessToken::Revert](../Topic/CAccessToken::Revert.md)|Appelez cette méthode pour arrêter un thread qui utilise un jeton d'emprunt d'identité.|  
|[CAccessToken::SetDefaultDacl](../Topic/CAccessToken::SetDefaultDacl.md)|Appelez cette méthode pour définir la valeur par défaut DACL de l'objet d' `CAccessToken` .|  
|[CAccessToken::SetOwner](../Topic/CAccessToken::SetOwner.md)|Appelez cette méthode pour définir le propriétaire de l'objet d' `CAccessToken` .|  
|[CAccessToken::SetPrimaryGroup](../Topic/CAccessToken::SetPrimaryGroup.md)|Appelez cette méthode pour définir le groupe principal de l'objet d' `CAccessToken` .|  
  
## Notes  
 [jeton d'accès](http://msdn.microsoft.com/library/windows/desktop/aa374909) est un objet qui décrit le contexte de sécurité d'un processus ou un thread et est alloué à chaque utilisateur stocké sur Windows NT ou un système Windows 2000.  
  
 Pour une introduction au modèle de contrôle d'accès dans windows, consultez [contrôle d'accès](http://msdn.microsoft.com/library/windows/desktop/aa374860) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Configuration requise  
 **Header:** atlsecurity.h  
  
## Voir aussi  
 [Exemple ATLSecurity](../../top/visual-cpp-samples.md)   
 [Access Tokens](http://msdn.microsoft.com/library/windows/desktop/aa374909)   
 [Class Overview](../../atl/atl-class-overview.md)