---
title: "Fonctions globales identificateur de sécurité | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- security IDs [C++]
- SIDs [C++], returning SID objects
ms.assetid: 85404dcb-c59b-4535-ab3d-66cfa37e87de
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 9e51fe30b0519514df34f1a77b1e731f51047520
ms.lasthandoff: 02/24/2017

---
# <a name="security-identifier-global-functions"></a>Fonctions globales identificateur de sécurité
Ces fonctions retournent des objets common SID bien connu.  
  
> [!IMPORTANT]
>  Les fonctions répertoriées dans le tableau suivant ne peut pas être utilisées dans les applications qui s’exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[SIDs::AccountOps](#accountops)|Retourne le SID de DOMAIN_ALIAS_RID_ACCOUNT_OPS.|  
|[SIDs::Admins](#admins)|Retourne le SID de DOMAIN_ALIAS_RID_ADMINS.|  
|[SIDs::AnonymousLogon](#anonymouslogon)|Retourne le SID de SECURITY_ANONYMOUS_LOGON_RID.|  
|[SIDs::AuthenticatedUser](#authenticateduser)|Retourne le SID de SECURITY_AUTHENTICATED_USER_RID.|  
|[SIDs::BackupOps](#backupops)|Retourne le SID de DOMAIN_ALIAS_RID_BACKUP_OPS.|  
|[SIDs::batch](#batch)|Retourne le SID de SECURITY_BATCH_RID.|  
|[SIDs::CreatorGroup](#creatorgroup)|Retourne le SID de SECURITY_CREATOR_GROUP_RID.|  
|[SIDs::CreatorGroupServer](#creatorgroupserver)|Retourne le SID de SECURITY_CREATOR_GROUP_SERVER_RID.|  
|[SIDs::CreatorOwner](#creatorowner)|Retourne le SID de SECURITY_CREATOR_OWNER_RID.|  
|[SIDs::CreatorOwnerServer](#creatorownerserver)|Retourne le SID de SECURITY_CREATOR_OWNER_SERVER_RID.|  
|[SIDs::Dialup](#dialup)|Retourne le SID de SECURITY_DIALUP_RID.|  
|[SIDs::Guests](#guests)|Retourne le SID de DOMAIN_ALIAS_RID_GUESTS.|  
|[SIDs::interactive](#interactive)|Retourne le SID de SECURITY_INTERACTIVE_RID.|  
|[SIDs::local](#local)|Retourne le SID de SECURITY_LOCAL_RID.|  
|[SIDs::Network](#network)|Retourne le SID de SECURITY_NETWORK_RID.|  
|[SIDs::NetworkService](#networkservice)|Retourne le SID de SECURITY_NETWORK_SERVICE_RID.|  
|[SIDs::null](#null)|Retourne le SID de SECURITY_NULL_RID.|  
|[SIDs::PreW2KAccess](#prew2kaccess)|Retourne le SID de DOMAIN_ALIAS_RID_PREW2KCOMPACCESS.|  
|[SIDs::PowerUsers](#powerusers)|Retourne le SID de DOMAIN_ALIAS_RID_POWER_USERS.|  
|[SIDs::PrintOps](#printops)|Retourne le SID de DOMAIN_ALIAS_RID_PRINT_OPS.|  
|[SIDs::proxy](#proxy)|Retourne le SID de SECURITY_PROXY_RID.|  
|[SIDs::RasServers](#rasservers)|Retourne le SID de DOMAIN_ALIAS_RID_RAS_SERVERS.|  
|[SIDs::Replicator](#replicator)|Retourne le SID de DOMAIN_ALIAS_RID_REPLICATOR.|  
|[SIDs::RestrictedCode](#restrictedcode)|Retourne le SID de SECURITY_RESTRICTED_CODE_RID.|  
|[SIDs::Self](#self)|Retourne le SID de SECURITY_PRINCIPAL_SELF_RID.|  
|[SIDs::ServerLogon](#serverlogon)|Retourne le SID de SECURITY_SERVER_LOGON_RID.|  
|[SIDs::service](#service)|Retourne le SID de SECURITY_SERVICE_RID.|  
|[SIDs::System](#system)|Retourne le SID de SECURITY_LOCAL_SYSTEM_RID.|  
|[SIDs::SystemOps](#systemops)|Retourne le SID de DOMAIN_ALIAS_RID_SYSTEM_OPS.|  
|[SIDs::TerminalServer](#terminalserver)|Retourne le SID de SECURITY_TERMINAL_SERVER_RID.|  
|[SIDs::Users](#users)|Retourne le SID de DOMAIN_ALIAS_RID_USERS.|  
|[SIDs::World](#world)|Retourne le SID de SECURITY_WORLD_RID.|  

### <a name="requirements"></a>Spécifications  
 **En-tête :** atlsecurity.h 

##  <a name="a-nameaccountopsa--sidsaccountops"></a><a name="accountops"></a>SIDs::AccountOps  
 Retourne le SID de DOMAIN_ALIAS_RID_ACCOUNT_OPS.    
  
```
CSid AccountOps() throw(...);
```  
  
##  <a name="a-nameadminsa--sidsadmins"></a><a name="admins"></a>SIDs::Admins  
 Retourne le SID de DOMAIN_ALIAS_RID_ADMINS.  
```
CSid Admins() throw(...);
```  
  
##  <a name="a-nameanonymouslogona--sidsanonymouslogon"></a><a name="anonymouslogon"></a>SIDs::AnonymousLogon  
 Retourne le SID de SECURITY_ANONYMOUS_LOGON_RID.  
```
CSid AnonymousLogon() throw(...);
```  
  
##  <a name="a-nameauthenticatedusera--sidsauthenticateduser"></a><a name="authenticateduser"></a>SIDs::AuthenticatedUser  
 Retourne le SID de SECURITY_AUTHENTICATED_USER_RID.  
```
CSid AuthenticatedUser() throw(...);
```  
  
##  <a name="a-namebackupopsa--sidsbackupops"></a><a name="backupops"></a>SIDs::BackupOps  
 Retourne le SID de DOMAIN_ALIAS_RID_BACKUP_OPS.  
```
CSid BackupOps() throw(...);
```  
  
##  <a name="a-namebatcha--sidsbatch"></a><a name="batch"></a>SIDs::batch  
 Retourne le SID de SECURITY_BATCH_RID.  
```
CSid Batch() throw(...);
```  
  
##  <a name="a-namecreatorgroupa--sidscreatorgroup"></a><a name="creatorgroup"></a>SIDs::CreatorGroup  
 Retourne le SID de SECURITY_CREATOR_GROUP_RID.  
```
CSid CreatorGroup() throw(...);
```  
  
##  <a name="a-namecreatorgroupservera--sidscreatorgroupserver"></a><a name="creatorgroupserver"></a>SIDs::CreatorGroupServer  
 Retourne le SID de SECURITY_CREATOR_GROUP_SERVER_RID.  
```
CSid CreatorGroupServer() throw(...);
```  
  
##  <a name="a-namecreatorownera--sidscreatorowner"></a><a name="creatorowner"></a>SIDs::CreatorOwner  
 Retourne le SID de SECURITY_CREATOR_OWNER_RID.  
```
CSid CreatorOwner() throw(...);
```  
  
##  <a name="a-namecreatorownerservera--sidscreatorownerserver"></a><a name="creatorownerserver"></a>SIDs::CreatorOwnerServer  
 Retourne le SID de SECURITY_CREATOR_OWNER_SERVER_RID.  
```
CSid CreatorOwnerServer() throw(...);
```  
  
##  <a name="a-namedialupa--sidsdialup"></a><a name="dialup"></a>SIDs::Dialup  
 Retourne le SID de SECURITY_DIALUP_RID.  
```
CSid Dialup() throw(...);
```  
  
##  <a name="a-nameguestsa--sidsguests"></a><a name="guests"></a>SIDs::Guests  
 Retourne le SID de DOMAIN_ALIAS_RID_GUESTS.  
```
CSid Guests() throw(...);
```  
  
##  <a name="a-nameinteractivea--sidsinteractive"></a><a name="interactive"></a>SIDs::interactive  
 Retourne le SID de SECURITY_INTERACTIVE_RID.  
```
CSid Interactive() throw(...);
```  
  
##  <a name="a-namelocala--sidslocal"></a><a name="local"></a>SIDs::local  
 Retourne le SID de SECURITY_LOCAL_RID.  
```
CSid Local() throw(...);
```  
  
##  <a name="a-namenetworka--sidsnetwork"></a><a name="network"></a>SIDs::Network  
 Retourne le SID de SECURITY_NETWORK_RID.  
```
CSid Network() throw(...);
```  
  
##  <a name="a-namenetworkservicea--sidsnetworkservice"></a><a name="networkservice"></a>SIDs::NetworkService  
 Retourne le SID de SECURITY_NETWORK_SERVICE_RID.  
```
CSid NetworkService() throw(...);
```  
  
### <a name="remarks"></a>Remarques  
 Utilisez NetworkService pour permettre à l’utilisateur NT AUTHORITY\NetworkService lire un objet de sécurité CPerfMon. NetworkService ajoute un SecurityAttribute au code ATL qui permettra à la DLL pour vous connecter sous le compte NetworkService sur [!INCLUDE[WinXpFamily](../../atl/reference/includes/winxpfamily_md.md)] et supérieure système d’exploitation.  
  
 Lorsque les compteurs de journal personnalisé sont créés avec la classe ATLServer CPerfMon dans la console MMC Perfmon, les compteurs peuvent être absentes lorsque vous affichez le fichier journal, bien qu’ils s’affichent correctement dans la vue en temps réel. Compteurs de performance personnalisés CPerfMon n’ont pas les autorisations nécessaires pour s’exécuter sous le service « Journaux et alertes de Performance » (smlogsvc.exe) [!INCLUDE[WinXpFamily](../../atl/reference/includes/winxpfamily_md.md)] (ou version ultérieure) systèmes d’exploitation. Ce service s’exécute sous le compte « NT AUTHORITY\NetworkService ».  
  
##  <a name="a-namenulla--sidsnull"></a><a name="null"></a>SIDs::null  
 Retourne le SID de SECURITY_NULL_RID.  
```
CSid Null() throw(...);
```  
  
##  <a name="a-nameprew2kaccessa--sidsprew2kaccess"></a><a name="prew2kaccess"></a>SIDs::PreW2KAccess  
 Retourne le SID de DOMAIN_ALIAS_RID_PREW2KCOMPACCESS.  
```
CSid PreW2KAccess() throw(...);
```  
  
##  <a name="a-namepowerusersa--sidspowerusers"></a><a name="powerusers"></a>SIDs::PowerUsers  
 Retourne le SID de DOMAIN_ALIAS_RID_POWER_USERS.  
```
CSid PowerUsers() throw(...);
```  
  
##  <a name="a-nameprintopsa--sidsprintops"></a><a name="printops"></a>SIDs::PrintOps  
 Retourne le SID de DOMAIN_ALIAS_RID_PRINT_OPS.  
```
CSid PrintOps() throw(...);
```  
  
##  <a name="a-nameproxya--sidsproxy"></a><a name="proxy"></a>SIDs::proxy  
 Retourne le SID de SECURITY_PROXY_RID.  
```
CSid Proxy() throw(...);
```  
  
##  <a name="a-namerasserversa--sidsrasservers"></a><a name="rasservers"></a>SIDs::RasServers  
 Retourne le SID de DOMAIN_ALIAS_RID_RAS_SERVERS.  
```
CSid RasServers() throw(...);
```  
  
##  <a name="a-namereplicatora--sidsreplicator"></a><a name="replicator"></a>SIDs::Replicator  
 Retourne le SID de DOMAIN_ALIAS_RID_REPLICATOR.  
```
CSid Replicator() throw(...);
```  
  
##  <a name="a-namerestrictedcodea--sidsrestrictedcode"></a><a name="restrictedcode"></a>SIDs::RestrictedCode  
 Retourne le SID de SECURITY_RESTRICTED_CODE_RID.  
```
CSid RestrictedCode() throw(...);
```  
  
##  <a name="a-nameselfa--sidsself"></a><a name="self"></a>SIDs::Self  
 Retourne le SID de SECURITY_PRINCIPAL_SELF_RID.  
```
CSid Self() throw(...);
```  
  
##  <a name="a-nameserverlogona--sidsserverlogon"></a><a name="serverlogon"></a>SIDs::ServerLogon  
 Retourne le SID de SECURITY_SERVER_LOGON_RID.  
```
CSid ServerLogon() throw(...);
```  
  
##  <a name="a-nameservicea--sidsservice"></a><a name="service"></a>SIDs::service  
 Retourne le SID de SECURITY_SERVICE_RID.  
```
CSid Service() throw(...);
```  
  
##  <a name="a-namesystema--sidssystem"></a><a name="system"></a>SIDs::System  
 Retourne le SID de SECURITY_LOCAL_SYSTEM_RID.  
```
CSid System() throw(...);
```  
  
##  <a name="a-namesystemopsa--sidssystemops"></a><a name="systemops"></a>SIDs::SystemOps  
 Retourne le SID de DOMAIN_ALIAS_RID_SYSTEM_OPS.  
```
CSid SystemOps() throw(...);
```  
  
##  <a name="a-nameterminalservera--sidsterminalserver"></a><a name="terminalserver"></a>SIDs::TerminalServer  
 Retourne le SID de SECURITY_TERMINAL_SERVER_RID.  
```
CSid TerminalServer() throw(...);
```  
  
##  <a name="a-nameusersa--sidsusers"></a><a name="users"></a>SIDs::Users  
 Retourne le SID de DOMAIN_ALIAS_RID_USERS.  
```
CSid Users() throw(...);
```  
  
##  <a name="a-nameworlda--sidsworld"></a><a name="world"></a>SIDs::World  
 Retourne le SID de SECURITY_WORLD_RID.  
```
CSid World() throw(...);
```  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions](../../atl/reference/atl-functions.md)

