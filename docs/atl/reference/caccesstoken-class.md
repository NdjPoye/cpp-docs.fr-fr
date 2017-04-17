---
title: Classe de CAccessToken | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAccessToken
- ATLSECURITY/ATL::CAccessToken
- ATLSECURITY/ATL::CAccessToken::Attach
- ATLSECURITY/ATL::CAccessToken::CheckTokenMembership
- ATLSECURITY/ATL::CAccessToken::CreateImpersonationToken
- ATLSECURITY/ATL::CAccessToken::CreatePrimaryToken
- ATLSECURITY/ATL::CAccessToken::CreateProcessAsUser
- ATLSECURITY/ATL::CAccessToken::CreateRestrictedToken
- ATLSECURITY/ATL::CAccessToken::Detach
- ATLSECURITY/ATL::CAccessToken::DisablePrivilege
- ATLSECURITY/ATL::CAccessToken::DisablePrivileges
- ATLSECURITY/ATL::CAccessToken::EnablePrivilege
- ATLSECURITY/ATL::CAccessToken::EnablePrivileges
- ATLSECURITY/ATL::CAccessToken::GetDefaultDacl
- ATLSECURITY/ATL::CAccessToken::GetEffectiveToken
- ATLSECURITY/ATL::CAccessToken::GetGroups
- ATLSECURITY/ATL::CAccessToken::GetHandle
- ATLSECURITY/ATL::CAccessToken::GetImpersonationLevel
- ATLSECURITY/ATL::CAccessToken::GetLogonSessionId
- ATLSECURITY/ATL::CAccessToken::GetLogonSid
- ATLSECURITY/ATL::CAccessToken::GetOwner
- ATLSECURITY/ATL::CAccessToken::GetPrimaryGroup
- ATLSECURITY/ATL::CAccessToken::GetPrivileges
- ATLSECURITY/ATL::CAccessToken::GetProcessToken
- ATLSECURITY/ATL::CAccessToken::GetProfile
- ATLSECURITY/ATL::CAccessToken::GetSource
- ATLSECURITY/ATL::CAccessToken::GetStatistics
- ATLSECURITY/ATL::CAccessToken::GetTerminalServicesSessionId
- ATLSECURITY/ATL::CAccessToken::GetThreadToken
- ATLSECURITY/ATL::CAccessToken::GetTokenId
- ATLSECURITY/ATL::CAccessToken::GetType
- ATLSECURITY/ATL::CAccessToken::GetUser
- ATLSECURITY/ATL::CAccessToken::HKeyCurrentUser
- ATLSECURITY/ATL::CAccessToken::Impersonate
- ATLSECURITY/ATL::CAccessToken::ImpersonateLoggedOnUser
- ATLSECURITY/ATL::CAccessToken::IsTokenRestricted
- ATLSECURITY/ATL::CAccessToken::LoadUserProfile
- ATLSECURITY/ATL::CAccessToken::LogonUser
- ATLSECURITY/ATL::CAccessToken::OpenCOMClientToken
- ATLSECURITY/ATL::CAccessToken::OpenNamedPipeClientToken
- ATLSECURITY/ATL::CAccessToken::OpenRPCClientToken
- ATLSECURITY/ATL::CAccessToken::OpenThreadToken
- ATLSECURITY/ATL::CAccessToken::PrivilegeCheck
- ATLSECURITY/ATL::CAccessToken::Revert
- ATLSECURITY/ATL::CAccessToken::SetDefaultDacl
- ATLSECURITY/ATL::CAccessToken::SetOwner
- ATLSECURITY/ATL::CAccessToken::SetPrimaryGroup
dev_langs:
- C++
helpviewer_keywords:
- CAccessToken class
ms.assetid: bb5c5945-56a5-4083-b442-76573cee83ab
caps.latest.revision: 24
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
ms.openlocfilehash: 79845a2be4f79a1ee94a9440e8508bcb0e38bcdd
ms.lasthandoff: 02/24/2017

---
# <a name="caccesstoken-class"></a>CAccessToken (classe)
Cette classe est un wrapper pour un jeton d’accès.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CAccessToken
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAccessToken :: ~ CAccessToken](#dtor)|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CAccessToken::Attach](#attach)|Appelez cette méthode pour s’approprier le handle de jeton d’accès donné.|  
|[CAccessToken::CheckTokenMembership](#checktokenmembership)|Appelez cette méthode pour déterminer si un SID spécifique est activé dans le `CAccessToken` objet.|  
|[CAccessToken::CreateImpersonationToken](#createimpersonationtoken)|Appelez cette méthode pour créer un nouveau jeton d’accès de l’emprunt d’identité.|  
|[CAccessToken::CreatePrimaryToken](#createprimarytoken)|Appelez cette méthode pour créer un jeton principal.|  
|[CAccessToken::CreateProcessAsUser](#createprocessasuser)|Appelez cette méthode pour créer un nouveau processus en cours d’exécution dans le contexte de sécurité de l’utilisateur représenté par le `CAccessToken` objet.|  
|[CAccessToken::CreateRestrictedToken](#createrestrictedtoken)|Appelez cette méthode pour créer un nouveau restreint `CAccessToken` objet.|  
|[CAccessToken::Detach](#detach)|Appelez cette méthode pour révoquer la possession du jeton d’accès.|  
|[CAccessToken::DisablePrivilege](#disableprivilege)|Appelez cette méthode pour désactiver un privilège dans le `CAccessToken` objet.|  
|[CAccessToken::DisablePrivileges](#disableprivileges)|Appelez cette méthode pour désactiver un ou plusieurs privilèges dans le `CAccessToken` objet.|  
|[CAccessToken::EnablePrivilege](#enableprivilege)|Appelez cette méthode pour activer un privilège dans le `CAccessToken` objet.|  
|[CAccessToken::EnablePrivileges](#enableprivileges)|Appelez cette méthode pour activer un ou plusieurs privilèges dans le `CAccessToken` objet.|  
|[CAccessToken::GetDefaultDacl](#getdefaultdacl)|Appelez cette méthode pour retourner le `CAccessToken` l’objet par défaut DACL.|  
|[CAccessToken::GetEffectiveToken](#geteffectivetoken)|Appelez cette méthode pour obtenir le `CAccessToken` objet égale au jeton d’accès en vigueur pour le thread actuel.|  
|[CAccessToken::GetGroups](#getgroups)|Appelez cette méthode pour retourner le `CAccessToken` groupes de jeton de l’objet.|  
|[CAccessToken::GetHandle](#gethandle)|Appelez cette méthode pour récupérer un handle pour le jeton d’accès.|  
|[CAccessToken::GetImpersonationLevel](#getimpersonationlevel)|Appelez cette méthode pour obtenir le niveau d’emprunt d’identité dans le jeton d’accès.|  
|[CAccessToken::GetLogonSessionId](#getlogonsessionid)|Appelez cette méthode pour obtenir l’ID de Session d’ouverture de session associé à le `CAccessToken` objet.|  
|[CAccessToken::GetLogonSid](#getlogonsid)|Appelez cette méthode pour obtenir le SID d’ouverture de session associé à le `CAccessToken` objet.|  
|[CAccessToken::GetOwner](#getowner)|Appelez cette méthode pour obtenir le propriétaire associé à le `CAccessToken` objet.|  
|[CAccessToken::GetPrimaryGroup](#getprimarygroup)|Appelez cette méthode pour obtenir le groupe principal associé à la `CAccessToken` objet.|  
|[CAccessToken::GetPrivileges](#getprivileges)|Appelez cette méthode pour obtenir les privilèges associés à le `CAccessToken` objet.|  
|[CAccessToken::GetProcessToken](#getprocesstoken)|Appelez cette méthode pour initialiser la `CAccessToken` avec le jeton d’accès du processus donné.|  
|[CAccessToken::GetProfile](#getprofile)|Appelez cette méthode pour obtenir le handle pointant vers le profil utilisateur associé à le `CAccessToken` objet.|  
|[CAccessToken::GetSource](#getsource)|Appelez cette méthode pour obtenir la source de la `CAccessToken` objet.|  
|[CAccessToken::GetStatistics](#getstatistics)|Appelez cette méthode pour obtenir des informations associées à la `CAccessToken` objet.|  
|[CAccessToken::GetTerminalServicesSessionId](#getterminalservicessessionid)|Appelez cette méthode pour obtenir l’ID de Session des Services Terminal Server associé à le `CAccessToken` objet.|  
|[CAccessToken::GetThreadToken](#getthreadtoken)|Appelez cette méthode pour initialiser la `CAccessToken` avec le jeton du thread donné.|  
|[CAccessToken::GetTokenId](#gettokenid)|Appelez cette méthode pour obtenir l’ID de jeton associé à le `CAccessToken` objet.|  
|[CAccessToken::GetType](#gettype)|Appelez cette méthode pour obtenir le type de jeton de le `CAccessToken` objet.|  
|[CAccessToken::GetUser](#getuser)|Appelez cette méthode pour identifier l’utilisateur associé à le `CAccessToken` objet.|  
|[CAccessToken::HKeyCurrentUser](#hkeycurrentuser)|Appelez cette méthode pour obtenir le handle pointant vers le profil utilisateur associé à le `CAccessToken` objet.|  
|[CAccessToken::Impersonate](#impersonate)|Appelez cette méthode pour affecter un emprunt d’identité `CAccessToken` à un thread.|  
|[CAccessToken::ImpersonateLoggedOnUser](#impersonateloggedonuser)|Appelez cette méthode pour permettre au thread appelant de l’identité du contexte de sécurité d’un utilisateur ayant ouvert une session.|  
|[CAccessToken::IsTokenRestricted](#istokenrestricted)|Appelez cette méthode pour tester si le `CAccessToken` objet contient une liste des SID limités.|  
|[CAccessToken::LoadUserProfile](#loaduserprofile)|Appelez cette méthode pour charger le profil utilisateur associé à le `CAccessToken` objet.|  
|[CAccessToken::LogonUser](#logonuser)|Appelez cette méthode pour créer une ouverture de session pour l’utilisateur associé les informations d’identification fournies.|  
|[CAccessToken::OpenCOMClientToken](#opencomclienttoken)|Appelez cette méthode à partir d’un serveur COM traite un appel d’un client pour initialiser la `CAccessToken` avec le jeton d’accès du client COM.|  
|[CAccessToken::OpenNamedPipeClientToken](#opennamedpipeclienttoken)|Appelez cette méthode à partir d’un serveur de prise de demandes via un canal nommé pour initialiser la `CAccessToken` avec le jeton d’accès à partir du client.|  
|[CAccessToken::OpenRPCClientToken](#openrpcclienttoken)|Appelez cette méthode à partir d’un serveur de gestion d’un appel à partir d’un client RPC pour initialiser la `CAccessToken` avec le jeton d’accès à partir du client.|  
|[CAccessToken::OpenThreadToken](#openthreadtoken)|Appelez cette méthode pour définir le niveau d’emprunt d’identité et d’initialiser la `CAccessToken` avec le jeton du thread donné.|  
|[CAccessToken::PrivilegeCheck](#privilegecheck)|Appelez cette méthode pour déterminer si un jeu défini de privilèges sont activés dans le **CAccessToken** objet.|  
|[CAccessToken::Revert](#revert)|Appelez cette méthode pour arrêter un thread qui utilise un jeton d’emprunt d’identité.|  
|[CAccessToken::SetDefaultDacl](#setdefaultdacl)|Appelez cette méthode pour définir la valeur par défaut DACL de le `CAccessToken` objet.|  
|[CAccessToken::SetOwner](#setowner)|Appelez cette méthode pour définir le propriétaire de la `CAccessToken` objet.|  
|[CAccessToken::SetPrimaryGroup](#setprimarygroup)|Appelez cette méthode pour définir le groupe principal de le `CAccessToken` objet.|  
  
## <a name="remarks"></a>Notes  
 Un [jeton d’accès](http://msdn.microsoft.com/library/windows/desktop/aa374909) est un objet qui décrit le contexte de sécurité d’un processus ou un thread et alloué à chaque utilisateur connecté à un système Windows NT ou Windows 2000.  
  
 Pour une présentation du modèle de contrôle d’accès dans Windows, consultez la page [le contrôle d’accès](http://msdn.microsoft.com/library/windows/desktop/aa374860) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlsecurity.h  
  
##  <a name="attach"></a>CAccessToken::Attach  
 Appelez cette méthode pour s’approprier le handle de jeton d’accès donné.  
  
```
void Attach(HANDLE hToken) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 *hToken*  
 Un handle pour le jeton d’accès.  
  
### <a name="remarks"></a>Notes  
 Dans les versions debug, une erreur d’assertion se produit si le `CAccessToken` objet déjà possède un jeton d’accès.  
  
##  <a name="dtor"></a>CAccessToken :: ~ CAccessToken  
 Destructeur.  
  
```
virtual ~CAccessToken() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Libère toutes les ressources attribuées.  
  
##  <a name="checktokenmembership"></a>CAccessToken::CheckTokenMembership  
 Appelez cette méthode pour déterminer si un SID spécifique est activé dans le `CAccessToken` objet.  
  
```
bool CheckTokenMembership(
    const CSid& rSid, 
    bool* pbIsMember) const throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `rSid`  
 Référence à un [CSid classe](../../atl/reference/csid-class.md) objet.  
  
 `pbIsMember`  
 Pointeur vers une variable qui reçoit les résultats de la vérification.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
### <a name="remarks"></a>Remarques  
 Le `CheckTokenMembership` méthode vérifie la présence du SID de l’utilisateur et le SID du jeton d’accès de groupe. Si le SID est présent et a l’attribut SE_GROUP_ENABLED, *pbIsMember* est la valeur true ; sinon, elle est définie sur false.  
  
 Dans les versions debug, une erreur d’assertion se produit si `pbIsMember` n’est pas un pointeur valide.  
  
> [!NOTE]
>  Le `CAccessToken` objet doit être un jeton d’emprunt d’identité et pas un jeton principal.  
  
##  <a name="createimpersonationtoken"></a>CAccessToken::CreateImpersonationToken  
 Appelez cette méthode pour créer un jeton d’accès de l’emprunt d’identité.  
  
```
bool CreateImpersonationToken(
    CAccessToken* pImp, 
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) const throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `pImp`  
 Pointeur vers la nouvelle `CAccessToken` objet.  
  
 `sil`  
 Spécifie un [SECURITY_IMPERSONATION_LEVEL](http://msdn.microsoft.com/library/windows/desktop/aa379572) type énuméré qui fournit le niveau d’emprunt d’identité du jeton de nouveau.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
### <a name="remarks"></a>Remarques  
 `CreateImpersonationToken`appels [DuplicateToken](http://msdn.microsoft.com/library/windows/desktop/aa446616) pour créer un jeton d’emprunt d’identité.  
  
##  <a name="createprimarytoken"></a>CAccessToken::CreatePrimaryToken  
 Appelez cette méthode pour créer un jeton principal.  
  
```
bool CreatePrimaryToken(
    CAccessToken* pPri,
    DWORD dwDesiredAccess = MAXIMUM_ALLOWED,
    const CSecurityAttributes* pTokenAttributes = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 *pPri*  
 Pointeur vers la nouvelle `CAccessToken` objet.  
  
 `dwDesiredAccess`  
 Spécifie les droits d’accès demandé pour le nouveau jeton. La valeur par défaut, MAXIMUM_ALLOWED, demandes de tous les droits d’accès qui sont valides pour l’appelant. Consultez [des droits d’accès et des masques d’accès](http://msdn.microsoft.com/library/windows/desktop/aa374902) pour sur plus de droits d’accès.  
  
 *pTokenAttributes*  
 Pointeur vers un [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) structure qui spécifie un descripteur de sécurité pour le nouveau jeton et détermine si des processus enfants peuvent hériter du jeton. Si *pTokenAttributes* est NULL, le jeton Obtient un descripteur de sécurité par défaut et le handle ne peut pas être hérité.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
### <a name="remarks"></a>Remarques  
 `CreatePrimaryToken`appels [DuplicateTokenEx](http://msdn.microsoft.com/library/windows/desktop/aa446617) pour créer un jeton principal.  
  
##  <a name="createprocessasuser"></a>CAccessToken::CreateProcessAsUser  
 Appelez cette méthode pour créer un nouveau processus en cours d’exécution dans le contexte de sécurité de l’utilisateur représenté par le `CAccessToken` objet.  
  
```
bool CreateProcessAsUser(
    LPCTSTR pApplicationName,
    LPTSTR pCommandLine,
    LPPROCESS_INFORMATION pProcessInformation,
    LPSTARTUPINFO pStartupInfo,
    DWORD dwCreationFlags = NORMAL_PRIORITY_CLASS,
    bool bLoadProfile = false,
    const CSecurityAttributes* pProcessAttributes = NULL,
    const CSecurityAttributes* pThreadAttributes = NULL,
    bool bInherit = false,
    LPCTSTR pCurrentDirectory = NULL) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 *pApplicationName*  
 Pointeur vers une chaîne terminée par le caractère null qui spécifie le module à exécuter. Ce paramètre ne peut pas être NULL.  
  
 *pCommandLine*  
 Pointeur vers une chaîne terminée par le caractère null qui spécifie la ligne de commande à exécuter.  
  
 *pProcessInformation*  
 Pointeur vers un [PROCESS_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/ms684873) structure qui reçoit des informations d’identification sur le nouveau processus.  
  
 *pStartupInfo*  
 Pointeur vers un [STARTUPINFO](http://msdn.microsoft.com/library/windows/desktop/ms686331) structure qui spécifie l’apparence de la fenêtre principale pour le nouveau processus.  
  
 `dwCreationFlags`  
 Spécifie des indicateurs supplémentaires qui contrôlent la classe de priorité et de la création du processus. Reportez-vous à la fonction Win32 [CreateProcessAsUser](http://msdn.microsoft.com/library/windows/desktop/ms682429) pour obtenir la liste d’indicateurs.  
  
 *bLoadProfile*  
 Si la valeur est true, le profil utilisateur est chargé avec [LoadUserProfile](http://msdn.microsoft.com/library/windows/desktop/bb762281).  
  
 *pProcessAttributes*  
 Pointeur vers un [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) structure qui spécifie un descripteur de sécurité pour le nouveau processus et détermine si des processus enfants peuvent hériter du handle retourné. Si *pProcessAttributes* est NULL, le processus obtient un descripteur de sécurité par défaut et le handle ne peut pas être hérité.  
  
 *pThreadAttributes*  
 Pointeur vers un [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) structure qui spécifie un descripteur de sécurité pour le nouveau thread et détermine si des processus enfants peuvent hériter du handle retourné. Si *pThreadAttributes* est NULL, le thread obtient un descripteur de sécurité par défaut et le handle ne peut pas être hérité.  
  
 *case bHériter*  
 Indique si le nouveau processus hérite des handles du processus appelant. Si la valeur est true, chaque handle ouvert pouvant être héritée dans le processus appelant est hérité par le nouveau processus. Handles hérités ont les mêmes privilèges d’accès et de valeur comme les handles d’origine.  
  
 *pCurrentDirectory*  
 Pointeur vers une chaîne terminée par le caractère null qui spécifie le lecteur en cours et le répertoire du nouveau processus. La chaîne doit être un chemin d’accès complet qui inclut une lettre de lecteur. Si ce paramètre est NULL, le nouveau processus aura le même lecteur et répertoire actifs que le processus appelant.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
### <a name="remarks"></a>Remarques  
 **CreateProcessAsUser** utilise le `CreateProcessAsUser` fonction Win32 pour créer un nouveau processus qui s’exécute dans le contexte de sécurité de l’utilisateur représenté par le `CAccessToken` objet. Consultez la description de la [CreateProcessAsUser](http://msdn.microsoft.com/library/windows/desktop/ms682429) (fonction) pour une description complète des paramètres requis.  
  
 Pour que cette méthode réussisse, le `CAccessToken` objet doit contenir AssignPrimaryToken (sauf si elle est un jeton restreint) et les privilèges de IncreaseQuota.  
  
##  <a name="createrestrictedtoken"></a>CAccessToken::CreateRestrictedToken  
 Appelez cette méthode pour créer un nouveau restreint `CAccessToken` objet.  
  
```
bool CreateRestrictedToken(
    CAccessToken* pRestrictedToken,
    const CTokenGroups& SidsToDisable,
    const CTokenGroups& SidsToRestrict,
    const CTokenPrivileges& PrivilegesToDelete = CTokenPrivileges()) const throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 *pRestrictedToken*  
 Restreint la nouvelle `CAccessToken` objet.  
  
 `SidsToDisable`  
 Un `CTokenGroups` objet qui spécifie le SID en refus seul.  
  
 *SidsToRestrict*  
 Un `CTokenGroups` objet qui spécifie le SID.  
  
 `PrivilegesToDelete`  
 Un `CTokenPrivileges` objet qui spécifie les privilèges à supprimer dans le jeton restreint. La valeur par défaut crée un objet vide.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
### <a name="remarks"></a>Remarques  
 `CreateRestrictedToken`utilise le [CreateRestrictedToken](http://msdn.microsoft.com/library/windows/desktop/aa446583) fonction Win32 pour créer un nouveau `CAccessToken` objet, sans restriction.  
  
> [!NOTE]
>  Cette méthode est uniquement disponible sur Windows 2000 ou version ultérieure.  
  
> [!IMPORTANT]
>  Lorsque vous utilisez `CreateRestrictedToken`, vérifiez les éléments suivants : le jeton existant est valide (et non entré par l’utilisateur) et `SidsToDisable` et `PrivilegesToDelete` sont valides (et non entré par l’utilisateur). Si la méthode retourne la valeur false, refuser la fonctionnalité.  
  
##  <a name="detach"></a>CAccessToken::Detach  
 Appelez cette méthode pour révoquer la possession du jeton d’accès.  
  
```
HANDLE Detach() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le handle vers le `CAccessToken` qui a été détaché.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode révoque le `CAccessToken`de propriété du jeton d’accès.  
  
##  <a name="disableprivilege"></a>CAccessToken::DisablePrivilege  
 Appelez cette méthode pour désactiver un privilège dans le `CAccessToken` objet.  
  
```
bool DisablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `pszPrivilege`  
 Pointeur vers une chaîne contenant le privilège désactive le `CAccessToken` objet.  
  
 `pPreviousState`  
 Pointeur vers un `CTokenPrivileges` objet qui contient l’état précédent des privilèges.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
##  <a name="disableprivileges"></a>CAccessToken::DisablePrivileges  
 Appelez cette méthode pour désactiver un ou plusieurs privilèges dans le `CAccessToken` objet.  
  
```
bool DisablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `rPrivileges`  
 Pointeur vers un tableau de chaînes contenant les privilèges désactive le `CAccessToken` objet.  
  
 `pPreviousState`  
 Pointeur vers un `CTokenPrivileges` objet qui contient l’état précédent des privilèges.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
##  <a name="enableprivilege"></a>CAccessToken::EnablePrivilege  
 Appelez cette méthode pour activer un privilège dans le `CAccessToken` objet.  
  
```
bool EnablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `pszPrivilege`  
 Pointeur vers une chaîne contenant le privilège à activer dans le `CAccessToken` objet.  
  
 `pPreviousState`  
 Pointeur vers un `CTokenPrivileges` objet qui contient l’état précédent des privilèges.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
##  <a name="enableprivileges"></a>CAccessToken::EnablePrivileges  
 Appelez cette méthode pour activer un ou plusieurs privilèges dans le `CAccessToken` objet.  
  
```
bool EnablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `rPrivileges`  
 Pointeur vers un tableau de chaînes contenant les privilèges pour l’activer dans le `CAccessToken` objet.  
  
 `pPreviousState`  
 Pointeur vers un `CTokenPrivileges` objet qui contient l’état précédent des privilèges.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
##  <a name="getdefaultdacl"></a>CAccessToken::GetDefaultDacl  
 Appelez cette méthode pour retourner le `CAccessToken` l’objet par défaut DACL.  
  
```
bool GetDefaultDacl(CDacl* pDacl) const throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDacl`  
 Pointeur vers le [CDacl classe](../../atl/reference/cdacl-class.md) objet qui reçoit le **CAccessToken** l’objet par défaut DACL.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true si la DACL par défaut a été récupérée.  
  
##  <a name="geteffectivetoken"></a>CAccessToken::GetEffectiveToken  
 Appelez cette méthode pour obtenir le `CAccessToken` objet égale au jeton d’accès en vigueur pour le thread actuel.  
  
```
bool GetEffectiveToken(DWORD dwDesiredAccess) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `dwDesiredAccess`  
 Spécifie un masque d’accès qui spécifie les types d’accès au jeton d’accès demandés. Ces types d’accès demandés sont comparés à la liste DACL du jeton pour déterminer quel accès sont accordés ou refusés.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
##  <a name="getgroups"></a>CAccessToken::GetGroups  
 Appelez cette méthode pour retourner le `CAccessToken` groupes de jeton de l’objet.  
  
```
bool GetGroups(CTokenGroups* pGroups) const throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 *pGroups*  
 Pointeur vers le [CTokenGroups classe](../../atl/reference/ctokengroups-class.md) objet qui reçoit les informations de groupe.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
##  <a name="gethandle"></a>CAccessToken::GetHandle  
 Appelez cette méthode pour récupérer un handle pour le jeton d’accès.  
  
```
HANDLE GetHandle() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un handle vers le `CAccessToken` jeton d’accès de l’objet.  
  
##  <a name="getimpersonationlevel"></a>CAccessToken::GetImpersonationLevel  
 Appelez cette méthode pour obtenir le niveau d’emprunt d’identité dans le jeton d’accès.  
  
```
bool GetImpersonationLevel(
    SECURITY_IMPERSONATION_LEVEL* pImpersonationLevel) const throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 *pImpersonationLevel*  
 Pointeur vers un [SECURITY_IMPERSONATION_LEVEL](http://msdn.microsoft.com/library/windows/desktop/aa379572) type d’énumération qui recevront les informations au niveau d’emprunt d’identité.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
##  <a name="getlogonsessionid"></a>CAccessToken::GetLogonSessionId  
 Appelez cette méthode pour obtenir l’ID de Session d’ouverture de session associé à le `CAccessToken` objet.  
  
```
bool GetLogonSessionId(LUID* pluid) const throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `pluid`  
 Pointeur vers un [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261) qui reçoit l’ID de Session d’ouverture de session.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
### <a name="remarks"></a>Remarques  
 Dans les versions debug, une erreur d’assertion se produit si `pluid` est une valeur non valide.  
  
##  <a name="getlogonsid"></a>CAccessToken::GetLogonSid  
 Appelez cette méthode pour obtenir le SID d’ouverture de session associé à le `CAccessToken` objet.  
  
```
bool GetLogonSid(CSid* pSid) const throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `pSid`  
 Pointeur vers un [CSid classe](../../atl/reference/csid-class.md) objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
### <a name="remarks"></a>Notes  
 Dans les versions debug, une erreur d’assertion se produit si *pSid* est une valeur non valide.  
  
##  <a name="getowner"></a>CAccessToken::GetOwner  
 Appelez cette méthode pour obtenir le propriétaire associé à le `CAccessToken` objet.  
  
```
bool GetOwner(CSid* pSid) const throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `pSid`  
 Pointeur vers un [CSid classe](../../atl/reference/csid-class.md) objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
### <a name="remarks"></a>Notes  
 Le propriétaire est défini par défaut sur tous les objets créés alors que ce jeton d’accès est en vigueur.  
  
##  <a name="getprimarygroup"></a>CAccessToken::GetPrimaryGroup  
 Appelez cette méthode pour obtenir le groupe principal associé à la `CAccessToken` objet.  
  
```
bool GetPrimaryGroup(CSid* pSid) const throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `pSid`  
 Pointeur vers un [CSid classe](../../atl/reference/csid-class.md) objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
### <a name="remarks"></a>Remarques  
 Le groupe est défini par défaut sur tous les objets créés alors que ce jeton d’accès est en vigueur.  
  
##  <a name="getprivileges"></a>CAccessToken::GetPrivileges  
 Appelez cette méthode pour obtenir les privilèges associés à le `CAccessToken` objet.  
  
```
bool GetPrivileges(CTokenPrivileges* pPrivileges) const throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `pPrivileges`  
 Pointeur vers un [CTokenPrivileges classe](../../atl/reference/ctokenprivileges-class.md) objet qui reçoit les privilèges.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
##  <a name="getprocesstoken"></a>CAccessToken::GetProcessToken  
 Appelez cette méthode pour initialiser la `CAccessToken` avec le jeton d’accès du processus donné.  
  
```
bool GetProcessToken(DWORD dwDesiredAccess, HANDLE hProcess = NULL) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `dwDesiredAccess`  
 Spécifie un masque d’accès qui spécifie les types d’accès au jeton d’accès demandés. Ces types d’accès demandés sont comparés à la liste DACL du jeton pour déterminer quel accès sont accordés ou refusés.  
  
 *hProcess*  
 Handle du processus dont le jeton d’accès est ouvert. Si la valeur par défaut de `NULL` est utilisée, le processus en cours est utilisé.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `true` en cas de réussite, `false` en cas d’échec.  
  
### <a name="remarks"></a>Remarques  
 Appelle le [OpenProcessToken](http://msdn.microsoft.com/library/aa379295\(vs.85\).aspx) fonction Win32.  
  
##  <a name="getprofile"></a>CAccessToken::GetProfile  
 Appelez cette méthode pour obtenir le handle pointant vers le profil utilisateur associé à le `CAccessToken` objet.  
  
```
HANDLE GetProfile() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un handle pointant vers le profil utilisateur, ou NULL si aucun profil n’existe.  
  
##  <a name="getsource"></a>CAccessToken::GetSource  
 Appelez cette méthode pour obtenir la source de la `CAccessToken` objet.  
  
```
bool GetSource(TOKEN_SOURCE* pSource) const throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 *pSource*  
 Pointeur vers un [TOKEN_SOURCE](http://msdn.microsoft.com/library/windows/desktop/aa379631) structure.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
##  <a name="getstatistics"></a>CAccessToken::GetStatistics  
 Appelez cette méthode pour obtenir des informations associées à la `CAccessToken` objet.  
  
```
bool GetStatistics(TOKEN_STATISTICS* pStatistics) const throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 *pStatistics*  
 Pointeur vers un [TOKEN_STATISTICS](http://msdn.microsoft.com/library/windows/desktop/aa379632) structure.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
##  <a name="getterminalservicessessionid"></a>CAccessToken::GetTerminalServicesSessionId  
 Appelez cette méthode pour obtenir l’ID de Session des Services Terminal Server associé à le `CAccessToken` objet.  
  
```
bool GetTerminalServicesSessionId(DWORD* pdwSessionId) const throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 *pdwSessionId*  
 L’ID de Session des Services Terminal Server.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
##  <a name="getthreadtoken"></a>CAccessToken::GetThreadToken  
 Appelez cette méthode pour initialiser la `CAccessToken` avec le jeton du thread donné.  
  
```
bool GetThreadToken(
    DWORD dwDesiredAccess,
    HANDLE hThread = NULL,
    bool bOpenAsSelf = true) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `dwDesiredAccess`  
 Spécifie un masque d’accès qui spécifie les types d’accès au jeton d’accès demandés. Ces types d’accès demandés sont comparés à la liste DACL du jeton pour déterminer quel accès sont accordés ou refusés.  
  
 `hThread`  
 Pointeur vers le thread dont le jeton d’accès est ouvert.  
  
 `bOpenAsSelf`  
 Indique si le contrôle d’accès doit être effectuée par rapport au contexte de sécurité de l’appel de thread la `GetThreadToken` méthode ou par rapport au contexte de sécurité du processus pour le thread appelant.  
  
 Si ce paramètre est false, le contrôle d’accès est effectué à l’aide du contexte de sécurité pour le thread appelant. Si le thread emprunte un client, ce contexte de sécurité peut être celui d’un processus client. Si ce paramètre est true, le contrôle d’accès est effectué à l’aide du contexte de sécurité du processus pour le thread appelant.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
##  <a name="gettokenid"></a>CAccessToken::GetTokenId  
 Appelez cette méthode pour obtenir l’ID de jeton associé à le `CAccessToken` objet.  
  
```
bool GetTokenId(LUID* pluid) const throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `pluid`  
 Pointeur vers un [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261) qui recevra le jeton ID.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
##  <a name="gettype"></a>CAccessToken::GetType  
 Appelez cette méthode pour obtenir le type de jeton de le `CAccessToken` objet.  
  
```
bool GetType(TOKEN_TYPE* pType) const throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `pType`  
 Adresse de la [TOKEN_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379633) variable qui, en cas de réussite, reçoit le type du jeton.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
### <a name="remarks"></a>Remarques  
 Le **TOKEN_TYPE** type énumération contient des valeurs qui divergent entre un jeton principal et un jeton d’emprunt d’identité.  
  
##  <a name="getuser"></a>CAccessToken::GetUser  
 Appelez cette méthode pour identifier l’utilisateur associé à le `CAccessToken` objet.  
  
```
bool GetUser(CSid* pSid) const throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `pSid`  
 Pointeur vers un [CSid classe](../../atl/reference/csid-class.md) objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
##  <a name="hkeycurrentuser"></a>CAccessToken::HKeyCurrentUser  
 Appelez cette méthode pour obtenir le handle pointant vers le profil utilisateur associé à le `CAccessToken` objet.  
  
```
HKEY HKeyCurrentUser() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un handle pointant vers le profil utilisateur, ou NULL si aucun profil n’existe.  
  
##  <a name="impersonate"></a>CAccessToken::Impersonate  
 Appelez cette méthode pour affecter un emprunt d’identité `CAccessToken` à un thread.  
  
```
bool Impersonate(HANDLE hThread = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `hThread`  
 Pointeur vers le thread pour affecter le jeton d’emprunt d’identité. Ce handle ait été ouvert avec des droits d’accès TOKEN_IMPERSONATE. Si `hThread` est NULL, la méthode oblige le thread arrêter d’utiliser un jeton d’emprunt d’identité.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
### <a name="remarks"></a>Remarques  
 Dans les versions debug, une erreur d’assertion se produit si `CAccessToken` ne dispose pas d’un pointeur vers un jeton valide.  
  
 Le [CAutoRevertImpersonation classe](../../atl/reference/cautorevertimpersonation-class.md) peut être utilisé pour rétablir automatiquement les jetons d’accès emprunt d’identité.  
  
##  <a name="impersonateloggedonuser"></a>CAccessToken::ImpersonateLoggedOnUser  
 Appelez cette méthode pour permettre au thread appelant de l’identité du contexte de sécurité d’un utilisateur ayant ouvert une session.  
  
```
bool ImpersonateLoggedOnUser() const throw(...);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
### <a name="remarks"></a>Remarques  
  
> [!IMPORTANT]
>  Si un appel à une fonction d’emprunt d’identité échoue pour une raison quelconque, le client n’est pas empruntée et la demande du client est effectuée dans le contexte de sécurité du processus à partir de laquelle l’appel a été effectué. Si le processus s’exécute sous un compte disposant de privilèges élevés, ou en tant que membre d’un groupe d’administration, l’utilisateur peut être en mesure d’effectuer des actions qu’il serait sinon être interdites. Par conséquent, la valeur de retour pour cette fonction doit toujours être confirmée.  
  
##  <a name="istokenrestricted"></a>CAccessToken::IsTokenRestricted  
 Appelez cette méthode pour tester si le `CAccessToken` objet contient une liste des SID limités.  
  
```
bool IsTokenRestricted() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne true si l’objet contient une liste de SID, false s’il n’y aucun SID restreints ou si la méthode échoue.  
  
##  <a name="loaduserprofile"></a>CAccessToken::LoadUserProfile  
 Appelez cette méthode pour charger le profil utilisateur associé à le `CAccessToken` objet.  
  
```
bool LoadUserProfile() throw(...);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
### <a name="remarks"></a>Notes  
 Dans les versions debug, une erreur d’assertion se produit si le `CAccessToken` ne contient pas un jeton valide, ou si un utilisateur de profil déjà existe.  
  
##  <a name="logonuser"></a>CAccessToken::LogonUser  
 Appelez cette méthode pour créer une ouverture de session pour l’utilisateur associé les informations d’identification fournies.  
  
```
bool LogonUser(
    LPCTSTR pszUserName,
    LPCTSTR pszDomain,
    LPCTSTR pszPassword,
    DWORD dwLogonType = LOGON32_LOGON_INTERACTIVE,
    DWORD dwLogonProvider = LOGON32_PROVIDER_DEFAULT) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `pszUserName`  
 Pointeur vers une chaîne terminée par le caractère null qui spécifie le nom d’utilisateur. Il s’agit du nom du compte d’utilisateur pour vous connecter à.  
  
 *pszDomain*  
 Pointeur vers une chaîne terminée par le caractère null qui spécifie le nom du domaine ou du serveur dont compte de base de données contient le `pszUserName` compte.  
  
 `pszPassword`  
 Pointeur vers une chaîne terminée par le caractère null qui spécifie le mot de passe en texte clair pour le compte d’utilisateur spécifié par `pszUserName`.  
  
 *dwLogonType*  
 Spécifie le type d’opération d’ouverture de session à effectuer. Consultez la page [LogonUser](http://msdn.microsoft.com/library/windows/desktop/aa378184) pour plus de détails.  
  
 *dwLogonProvider*  
 Spécifie le fournisseur d’ouverture de session. Consultez la page [LogonUser](http://msdn.microsoft.com/library/windows/desktop/aa378184) pour plus de détails.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
### <a name="remarks"></a>Remarques  
 L’accès au jeton résultant de l’ouverture de session sera associé le `CAccessToken`. Pour que cette méthode réussisse, le `CAccessToken` objet doit contenir des privilèges SE_TCB_NAME, identifier le titulaire dans le cadre de l’ordinateur de base approuvée. Consultez la page [LogonUser](http://msdn.microsoft.com/library/windows/desktop/aa378184) pour plus d’informations sur les privilèges requis.  
  
##  <a name="opencomclienttoken"></a>CAccessToken::OpenCOMClientToken  
 Appelez cette méthode à partir d’un serveur COM traite un appel d’un client pour initialiser la `CAccessToken` avec le jeton d’accès du client COM.  
  
```
bool OpenCOMClientToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwDesiredAccess`  
 Spécifie un masque d’accès qui spécifie les types d’accès au jeton d’accès demandés. Ces types d’accès demandés sont comparés à la liste DACL du jeton pour déterminer quel accès sont accordés ou refusés.  
  
 `bImpersonate`  
 Si la valeur est true, le thread actuel empruntera le client COM appelant si cet appel s’effectue correctement. Si la valeur est false, le jeton d’accès s’ouvre, mais le thread ne dispose d’un jeton d’emprunt d’identité lorsque cet appel est terminé.  
  
 `bOpenAsSelf`  
 Indique si le contrôle d’accès doit être effectuée par rapport au contexte de sécurité de l’appel de thread la [GetThreadToken](http://msdn.microsoft.com/library/windows/desktop/ms683182) méthode ou par rapport au contexte de sécurité du processus pour le thread appelant.  
  
 Si ce paramètre est false, le contrôle d’accès est effectué à l’aide du contexte de sécurité pour le thread appelant. Si le thread emprunte un client, ce contexte de sécurité peut être celui d’un processus client. Si ce paramètre est true, le contrôle d’accès est effectué à l’aide du contexte de sécurité du processus pour le thread appelant.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
### <a name="remarks"></a>Notes  
 Le [CAutoRevertImpersonation classe](../../atl/reference/cautorevertimpersonation-class.md) peut être utilisé pour rétablir automatiquement les jetons d’accès emprunté créés en définissant le `bImpersonate` indicateur *true*.  
  
##  <a name="opennamedpipeclienttoken"></a>CAccessToken::OpenNamedPipeClientToken  
 Appelez cette méthode à partir d’un serveur de prise de demandes via un canal nommé pour initialiser la `CAccessToken` avec le jeton d’accès à partir du client.  
  
```
bool OpenNamedPipeClientToken(
    HANDLE hPipe,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 *hPipe*  
 Handle vers un canal nommé.  
  
 `dwDesiredAccess`  
 Spécifie un masque d’accès qui spécifie les types d’accès au jeton d’accès demandés. Ces types d’accès demandés sont comparés à la liste DACL du jeton pour déterminer quel accès sont accordés ou refusés.  
  
 `bImpersonate`  
 Si la valeur est true, le thread actuel sera emprunter l’identité du client canal si cet appel s’effectue correctement. Si la valeur est false, le jeton d’accès s’ouvre, mais le thread ne dispose d’un jeton d’emprunt d’identité lorsque cet appel est terminé.  
  
 `bOpenAsSelf`  
 Indique si le contrôle d’accès doit être effectuée par rapport au contexte de sécurité de l’appel de thread la [GetThreadToken](http://msdn.microsoft.com/library/windows/desktop/ms683182) méthode ou par rapport au contexte de sécurité du processus pour le thread appelant.  
  
 Si ce paramètre est false, le contrôle d’accès est effectué à l’aide du contexte de sécurité pour le thread appelant. Si le thread emprunte un client, ce contexte de sécurité peut être celui d’un processus client. Si ce paramètre est true, le contrôle d’accès est effectué à l’aide du contexte de sécurité du processus pour le thread appelant.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
### <a name="remarks"></a>Remarques  
 Le [CAutoRevertImpersonation classe](../../atl/reference/cautorevertimpersonation-class.md) peut être utilisé pour rétablir automatiquement les jetons d’accès emprunté créés en définissant le `bImpersonate` indicateur *true*.  
  
##  <a name="openrpcclienttoken"></a>CAccessToken::OpenRPCClientToken  
 Appelez cette méthode à partir d’un serveur de gestion d’un appel à partir d’un client RPC pour initialiser la `CAccessToken` avec le jeton d’accès à partir du client.  
  
```
bool OpenRPCClientToken(
    RPC_BINDING_HANDLE BindingHandle,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 *BindingHandle*  
 Handle de liaison sur le serveur qui représente une liaison à un client.  
  
 `dwDesiredAccess`  
 Spécifie un masque d’accès qui spécifie les types d’accès au jeton d’accès demandés. Ces types d’accès demandés sont comparés à la liste DACL du jeton pour déterminer quel accès sont accordés ou refusés.  
  
 `bImpersonate`  
 Si la valeur est true, le thread actuel est emprunter l’identité du client RPC si cet appel s’effectue correctement. Si la valeur est false, le jeton d’accès s’ouvre, mais le thread ne dispose d’un jeton d’emprunt d’identité lorsque cet appel est terminé.  
  
 `bOpenAsSelf`  
 Indique si le contrôle d’accès doit être effectuée par rapport au contexte de sécurité de l’appel de thread la [GetThreadToken](http://msdn.microsoft.com/library/windows/desktop/ms683182) méthode ou par rapport au contexte de sécurité du processus pour le thread appelant.  
  
 Si ce paramètre est false, le contrôle d’accès est effectué à l’aide du contexte de sécurité pour le thread appelant. Si le thread emprunte un client, ce contexte de sécurité peut être celui d’un processus client. Si ce paramètre est true, le contrôle d’accès est effectué à l’aide du contexte de sécurité du processus pour le thread appelant.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
### <a name="remarks"></a>Remarques  
 Le [CAutoRevertImpersonation classe](../../atl/reference/cautorevertimpersonation-class.md) peut être utilisé pour rétablir automatiquement les jetons d’accès emprunté créés en définissant le `bImpersonate` indicateur *true*.  
  
##  <a name="openthreadtoken"></a>CAccessToken::OpenThreadToken  
 Appelez cette méthode pour définir le niveau d’emprunt d’identité et d’initialiser la `CAccessToken` avec le jeton du thread donné.  
  
```
bool OpenThreadToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true,
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwDesiredAccess`  
 Spécifie un masque d’accès qui spécifie les types d’accès au jeton d’accès demandés. Ces types d’accès demandés sont comparés à la liste DACL du jeton pour déterminer quel accès sont accordés ou refusés.  
  
 `bImpersonate`  
 Si la valeur est true, le thread reste au niveau d’emprunt d’identité demandé une fois cette méthode terminée. Si la valeur est false, le thread reviendra à son niveau d’emprunt d’identité d’origine.  
  
 `bOpenAsSelf`  
 Indique si le contrôle d’accès doit être effectuée par rapport au contexte de sécurité de l’appel de thread la [GetThreadToken](http://msdn.microsoft.com/library/windows/desktop/ms683182) méthode ou par rapport au contexte de sécurité du processus pour le thread appelant.  
  
 Si ce paramètre est false, le contrôle d’accès est effectué à l’aide du contexte de sécurité pour le thread appelant. Si le thread emprunte un client, ce contexte de sécurité peut être celui d’un processus client. Si ce paramètre est true, le contrôle d’accès est effectué à l’aide du contexte de sécurité du processus pour le thread appelant.  
  
 `sil`  
 Spécifie un [SECURITY_IMPERSONATION_LEVEL](http://msdn.microsoft.com/library/windows/desktop/aa379572) type énuméré qui fournit le niveau d’emprunt d’identité du jeton.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
### <a name="remarks"></a>Remarques  
 `OpenThreadToken`est semblable à [CAccessToken::GetThreadToken](#getthreadtoken), mais définit le niveau d’emprunt d’identité avant d’initialiser le `CAccessToken` à partir du jeton d’accès du thread.  
  
 Le [CAutoRevertImpersonation classe](../../atl/reference/cautorevertimpersonation-class.md) peut être utilisé pour rétablir automatiquement les jetons d’accès emprunté créés en définissant le `bImpersonate` indicateur *true*.  
  
##  <a name="privilegecheck"></a>CAccessToken::PrivilegeCheck  
 Appelez cette méthode pour déterminer si un jeu défini de privilèges sont activés dans le **CAccessToken** objet.  
  
```
bool PrivilegeCheck(
    PPRIVILEGE_SET RequiredPrivileges,
     bool* pbResult) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 *RequiredPrivileges*  
 Pointeur vers un [PRIVILEGE_SET](http://msdn.microsoft.com/library/windows/desktop/aa379307) structure.  
  
 *pbResult*  
 Pointeur vers une valeur de la méthode définit pour indiquer si tout ou partie du privilège spécifié sont activés dans le `CAccessToken` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
### <a name="remarks"></a>Remarques  
 Lors de la `PrivilegeCheck` retourne, le **attributs** membre de chaque [LUID_AND_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379263) structure a la valeur SE_PRIVILEGE_USED_FOR_ACCESS si le privilège correspondant est activé. Cette méthode appelle la [PrivilegeCheck](http://msdn.microsoft.com/library/windows/desktop/aa379304) fonction Win32.  
  
##  <a name="revert"></a>CAccessToken::Revert  
 Appelez cette méthode pour arrêter un thread à l’aide d’un jeton d’emprunt d’identité.  
  
```
bool Revert(HANDLE hThread = NULL) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `hThread`  
 Pointeur vers le thread pour rétablir l’emprunt d’identité. Si *hThread* est NULL, le thread actuel est supposé.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
### <a name="remarks"></a>Notes  
 L’inversion des jetons d’emprunt d’identité peut être effectuée automatiquement avec les [CAutoRevertImpersonation classe](../../atl/reference/cautorevertimpersonation-class.md).  
  
##  <a name="setdefaultdacl"></a>CAccessToken::SetDefaultDacl  
 Appelez cette méthode pour définir la valeur par défaut DACL de le `CAccessToken` objet.  
  
```
bool SetDefaultDacl(const CDacl& rDacl) throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `rDacl`  
 La nouvelle valeur par défaut [CDacl classe](../../atl/reference/cdacl-class.md) plus d’informations.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
### <a name="remarks"></a>Remarques  
 La DACL est la DACL est utilisée par défaut lorsque de nouveaux objets sont créés avec ce jeton d’accès en vigueur.  
  
##  <a name="setowner"></a>CAccessToken::SetOwner  
 Appelez cette méthode pour définir le propriétaire de la `CAccessToken` objet.  
  
```
bool SetOwner(const CSid& rSid) throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `rSid`  
 Le [CSid classe](../../atl/reference/csid-class.md) objet contenant les informations de propriétaire.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
### <a name="remarks"></a>Notes  
 Le propriétaire est le propriétaire par défaut qui est utilisé pour les nouveaux objets créés alors que ce jeton d’accès est en vigueur.  
  
##  <a name="setprimarygroup"></a>CAccessToken::SetPrimaryGroup  
 Appelez cette méthode pour définir le groupe principal de le `CAccessToken` objet.  
  
```
bool SetPrimaryGroup(const CSid& rSid) throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `rSid`  
 Le [CSid classe](../../atl/reference/csid-class.md) objet contenant les informations de groupe principal.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
### <a name="remarks"></a>Remarques  
 Le groupe principal est le groupe par défaut pour les nouveaux objets créés alors que ce jeton d’accès est en vigueur.  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple ATLSecurity](../../visual-cpp-samples.md)   
 [Jetons d’accès](http://msdn.microsoft.com/library/windows/desktop/aa374909)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)
