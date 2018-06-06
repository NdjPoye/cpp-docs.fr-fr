---
title: Classe de CAtlServiceModuleT | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlServiceModuleT
- ATLBASE/ATL::CAtlServiceModuleT
- ATLBASE/ATL::CAtlServiceModuleT::CAtlServiceModuleT
- ATLBASE/ATL::CAtlServiceModuleT::Handler
- ATLBASE/ATL::CAtlServiceModuleT::InitializeSecurity
- ATLBASE/ATL::CAtlServiceModuleT::Install
- ATLBASE/ATL::CAtlServiceModuleT::IsInstalled
- ATLBASE/ATL::CAtlServiceModuleT::LogEvent
- ATLBASE/ATL::CAtlServiceModuleT::OnContinue
- ATLBASE/ATL::CAtlServiceModuleT::OnInterrogate
- ATLBASE/ATL::CAtlServiceModuleT::OnPause
- ATLBASE/ATL::CAtlServiceModuleT::OnShutdown
- ATLBASE/ATL::CAtlServiceModuleT::OnStop
- ATLBASE/ATL::CAtlServiceModuleT::OnUnknownRequest
- ATLBASE/ATL::CAtlServiceModuleT::ParseCommandLine
- ATLBASE/ATL::CAtlServiceModuleT::PreMessageLoop
- ATLBASE/ATL::CAtlServiceModuleT::RegisterAppId
- ATLBASE/ATL::CAtlServiceModuleT::Run
- ATLBASE/ATL::CAtlServiceModuleT::ServiceMain
- ATLBASE/ATL::CAtlServiceModuleT::SetServiceStatus
- ATLBASE/ATL::CAtlServiceModuleT::Start
- ATLBASE/ATL::CAtlServiceModuleT::Uninstall
- ATLBASE/ATL::CAtlServiceModuleT::Unlock
- ATLBASE/ATL::CAtlServiceModuleT::UnregisterAppId
- ATLBASE/ATL::CAtlServiceModuleT::WinMain
- ATLBASE/ATL::CAtlServiceModuleT::m_bService
- ATLBASE/ATL::CAtlServiceModuleT::m_dwThreadID
- ATLBASE/ATL::CAtlServiceModuleT::m_hServiceStatus
- ATLBASE/ATL::CAtlServiceModuleT::m_status
- ATLBASE/ATL::CAtlServiceModuleT::m_szServiceName
dev_langs:
- C++
helpviewer_keywords:
- CAtlServiceModuleT class
ms.assetid: 8fc753ce-4a50-402b-9b4a-0a4ce5dd496c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c81df88dfdf2b40b5196d219159b48023d9db6d4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="catlservicemodulet-class"></a>Classe de CAtlServiceModuleT
Cette classe implémente un service.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class T, UINT nServiceNameID>  
class ATL_NO_VTABLE CAtlServiceModuleT : public CAtlExeModuleT<T>
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Votre classe dérivée de `CAtlServiceModuleT`.  
  
 *nServiceNameID*  
 L’identificateur de ressource du service.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlServiceModuleT::CAtlServiceModuleT](#catlservicemodulet)|Constructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlServiceModuleT::Handler](#handler)|La routine du gestionnaire pour le service.|  
|[CAtlServiceModuleT::InitializeSecurity](#initializesecurity)|Fournit la valeur par défaut des paramètres de sécurité pour le service.|  
|[CAtlServiceModuleT::Install](#install)|Installe et crée le service.|  
|[CAtlServiceModuleT::IsInstalled](#isinstalled)|Confirme que le service a été installé.|  
|[CAtlServiceModuleT::LogEvent](#logevent)|Écrit dans le journal des événements.|  
|[CAtlServiceModuleT::OnContinue](#oncontinue)|Substituez cette méthode pour reprendre le service.|  
|[CAtlServiceModuleT::OnInterrogate](#oninterrogate)|Substituez cette méthode pour interroger le service.|  
|[CAtlServiceModuleT::OnPause](#onpause)|Substituez cette méthode pour suspendre le service.|  
|[CAtlServiceModuleT::OnShutdown](#onshutdown)|Substituez cette méthode pour arrêter le service|  
|[CAtlServiceModuleT::OnStop](#onstop)|Substituez cette méthode pour arrêter le service|  
|[CAtlServiceModuleT::OnUnknownRequest](#onunknownrequest)|Substituez cette méthode pour gérer les demandes au service inconnus|  
|[CAtlServiceModuleT::ParseCommandLine](#parsecommandline)|Analyse de la ligne de commande et effectue l’inscription si nécessaire.|  
|[CAtlServiceModuleT::PreMessageLoop](#premessageloop)|Cette méthode est appelée immédiatement avant d’entrer dans la boucle de message.|  
|[CAtlServiceModuleT::RegisterAppId](#registerappid)|Inscrit le service dans le Registre.|  
|[CAtlServiceModuleT::Run](#run)|Exécute le service.|  
|[CAtlServiceModuleT::ServiceMain](#servicemain)|La méthode appelée par le Gestionnaire de contrôle de Service.|  
|[CAtlServiceModuleT::SetServiceStatus](#setservicestatus)|Met à jour l’état du service.|  
|[CAtlServiceModuleT::Start](#start)|Appelé par `CAtlServiceModuleT::WinMain` lorsque le service démarre.|  
|[CAtlServiceModuleT::Uninstall](#uninstall)|Arrête et supprime le service.|  
|[CAtlServiceModuleT::Unlock](#unlock)|Décrémente de nombre de verrous du service.|  
|[CAtlServiceModuleT::UnregisterAppId](#unregisterappid)|Supprime le service à partir du Registre.|  
|[CAtlServiceModuleT::WinMain](#winmain)|Cette méthode implémente le code requis pour exécuter le service.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlServiceModuleT::m_bService](#m_bservice)|Indicateur qui spécifie que le programme s’exécute en tant que service.|  
|[CAtlServiceModuleT::m_dwThreadID](#m_dwthreadid)|Variable membre le stockage de l’identificateur du thread.|  
|[CAtlServiceModuleT::m_hServiceStatus](#m_hservicestatus)|Variable membre le stockage d’un handle vers la structure d’information de statut pour le service en cours.|  
|[CAtlServiceModuleT::m_status](#m_status)|Variable membre le stockage de la structure d’information de statut pour le service en cours.|  
|[CAtlServiceModuleT::m_szServiceName](#m_szservicename)|Le nom du service en cours d’inscription.|  
  
## <a name="remarks"></a>Notes  
 `CAtlServiceModuleT`, dérivé de [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md), implémente un module de Service ATL. `CAtlServiceModuleT` Fournit des méthodes pour le traitement de ligne de commande, l’installation, l’inscription et la suppression. Si des fonctionnalités supplémentaires sont requises, celles-ci et autres méthodes peuvent être substituées.  
  
 Cette classe remplace l’obsolète [CComModule (classe)](../../atl/reference/ccommodule-class.md) utilisé dans les versions antérieures d’ATL. Consultez [Module ATL, Classes](../../atl/atl-module-classes.md) pour plus d’informations.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)  
  
 `CAtlServiceModuleT`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h  
  
##  <a name="catlservicemodulet"></a>  CAtlServiceModuleT::CAtlServiceModuleT  
 Constructeur.  
  
```
CAtlServiceModuleT() throw();
```  
  
### <a name="remarks"></a>Notes  
 Initialise les membres de données et définit l’état du service initial.  
  
##  <a name="handler"></a>  CAtlServiceModuleT::Handler  
 La routine du gestionnaire pour le service.  
  
```
void Handler(DWORD dwOpcode) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 *dwOpcode*  
 Un commutateur qui définit l’opération de gestionnaire. Pour plus d’informations, consultez la section Notes.  
  
### <a name="remarks"></a>Notes  
 Voici le code qui appelle par le Gestionnaire de contrôle des services (SCM) pour récupérer l’état des instructions de service et le problème comme arrêter ou suspendre. Le SCM passe un code d’opération, illustré ci-dessous, à `Handler` pour indiquer comme le service.  
  
|Code d’opération|Signification|  
|--------------------|-------------|  
|SERVICE_CONTROL_STOP|Arrête le service. Substituez la méthode [CAtlServiceModuleT::OnStop](#onstop) dans atlbase.h pour modifier le comportement.|  
|SERVICE_CONTROL_PAUSE|Implémenté de l’utilisateur. Substituez la méthode vide [CAtlServiceModuleT::OnPause](#onpause) dans atlbase.h pour interrompre le service.|  
|SERVICE_CONTROL_CONTINUE|Implémenté de l’utilisateur. Substituez la méthode vide [CAtlServiceModuleT::OnContinue](#oncontinue) dans atlbase.h pour reprendre le service.|  
|SERVICE_CONTROL_INTERROGATE|Implémenté de l’utilisateur. Substituez la méthode vide [CAtlServiceModuleT::OnInterrogate](#oninterrogate) dans atlbase.h pour interroger le service.|  
|SERVICE_CONTROL_SHUTDOWN|Implémenté de l’utilisateur. Substituez la méthode vide [CAtlServiceModuleT::OnShutdown](#onshutdown) dans atlbase.h d’arrêt du service.|  
  
 Si le code d’opération n’est pas reconnu, la méthode [CAtlServiceModuleT::OnUnknownRequest](#onunknownrequest) est appelée.  
  
 Un service de généré ATL par défaut gère uniquement l’instruction d’arrêt. Si le SCM passe l’instruction d’arrêt, le service indique au SCM que le programme est sur le point d’arrêt. Le service appelle ensuite `PostThreadMessage` pour publier un message à elle-même. Cela met fin à la boucle de messages et le service se ferme définitivement.  
  
##  <a name="initializesecurity"></a>  CAtlServiceModuleT::InitializeSecurity  
 Fournit la valeur par défaut des paramètres de sécurité pour le service.  
  
```
HRESULT InitializeSecurity() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Dans Visual Studio .NET 2003, cette méthode n’est pas implémentée dans la classe de base. L’Assistant projet Visual Studio inclut cette méthode dans le code généré, mais une erreur de compilation se produit si un projet créé dans une version antérieure de Visual C++ est compilé à l’aide de ATL 7.1. Toute classe qui dérive de `CAtlServiceModuleT` doit implémenter cette méthode dans la classe dérivée.  
  
 Utiliser l’authentification de niveau PKT, niveau d’emprunt d’identité RPC_C_IMP_LEVEL_IDENTIFY et un descripteur de sécurité non null appropriés dans l’appel à **CoInitializeSecurity**.  
  
 Pour les projets générés par l’Assistant de service sans attributs, il s’agit de  
  
 [!code-cpp[NVC_ATL_Service#1](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_1.cpp)]  
  
 Pour les projets de service avec attributs, cela serait  
  
 [!code-cpp[NVC_ATL_ServiceAttrib#1](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_2.cpp)]  
  
##  <a name="install"></a>  CAtlServiceModuleT::Install  
 Installe et crée le service.  
  
```
BOOL Install() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur TRUE en cas de réussite, FALSE en cas d’échec.  
  
### <a name="remarks"></a>Notes  
 Installe le service dans la base de données du Gestionnaire de contrôle des services (SCM), puis crée l’objet de service. Si le service n’a pas pu être créé, un message s’affiche et la méthode retourne FALSE.  
  
##  <a name="isinstalled"></a>  CAtlServiceModuleT::IsInstalled  
 Confirme que le service a été installé.  
  
```
BOOL IsInstalled() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur TRUE si le service est installé, la valeur FALSE.  
  
##  <a name="logevent"></a>  CAtlServiceModuleT::LogEvent  
 Écrit dans le journal des événements.  
  
```
void __cdecl LogEvent(LPCTSTR pszFormat, ...) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `pszFormat`  
 Chaîne à écrire dans le journal des événements.  
  
 ...  
 Chaînes supplémentaires facultatif à écrire dans le journal des événements.  
  
### <a name="remarks"></a>Notes  
 Cette méthode écrit détails dans un journal des événements, à l’aide de la fonction [ReportEvent](http://msdn.microsoft.com/library/windows/desktop/aa363679). Si aucun service n’est en cours d’exécution, la chaîne est envoyée à la console.  
  
##  <a name="m_bservice"></a>  CAtlServiceModuleT::m_bService  
 Indicateur qui spécifie que le programme s’exécute en tant que service.  
  
```
BOOL m_bService;
```  
  
### <a name="remarks"></a>Notes  
 Utilisé pour distinguer un EXE de Service à partir d’un EXE d’Application.  
  
##  <a name="m_dwthreadid"></a>  CAtlServiceModuleT::m_dwThreadID  
 Variable membre le stockage de l’identificateur du thread du Service.  
  
```
DWORD m_dwThreadID;
```  
  
### <a name="remarks"></a>Notes  
 Cette variable stocke l’identificateur du thread du thread actuel.  
  
##  <a name="m_hservicestatus"></a>  CAtlServiceModuleT::m_hServiceStatus  
 Variable membre le stockage d’un handle vers la structure d’information de statut pour le service en cours.  
  
```
SERVICE_STATUS_HANDLE m_hServiceStatus;
```  
  
### <a name="remarks"></a>Notes  
 Le [SERVICE_STATUS](http://msdn.microsoft.com/library/windows/desktop/ms685996) structure contient des informations sur un service.  
  
##  <a name="m_status"></a>  CAtlServiceModuleT::m_status  
 Variable membre le stockage de la structure d’information de statut pour le service en cours.  
  
```
SERVICE_STATUS m_status;
```  
  
### <a name="remarks"></a>Notes  
 Le [SERVICE_STATUS](http://msdn.microsoft.com/library/windows/desktop/ms685996) structure contient des informations sur un service.  
  
##  <a name="m_szservicename"></a>  CAtlServiceModuleT::m_szServiceName  
 Le nom du service en cours d’inscription.  
  
```
TCHAR [256] m_szServiceName;
```  
  
### <a name="remarks"></a>Notes  
 Une chaîne se terminant par null qui stocke le nom du service.  
  
##  <a name="oncontinue"></a>  CAtlServiceModuleT::OnContinue  
 Substituez cette méthode pour reprendre le service.  
  
```
void OnContinue() throw();
```  
  
##  <a name="oninterrogate"></a>  CAtlServiceModuleT::OnInterrogate  
 Substituez cette méthode pour interroger le service.  
  
```
void OnInterrogate() throw();
```  
  
##  <a name="onpause"></a>  CAtlServiceModuleT::OnPause  
 Substituez cette méthode pour suspendre le service.  
  
```
void OnPause() throw();
```  
  
##  <a name="onshutdown"></a>  CAtlServiceModuleT::OnShutdown  
 Substituez cette méthode pour arrêter le service.  
  
```
void OnShutdown() throw();
```  
  
##  <a name="onstop"></a>  CAtlServiceModuleT::OnStop  
 Substituez cette méthode pour arrêter le service.  
  
```
void OnStop() throw();
```  
  
##  <a name="onunknownrequest"></a>  CAtlServiceModuleT::OnUnknownRequest  
 Substituez cette méthode pour gérer les demandes inconnus pour le service.  
  
```
void OnUnknownRequest(DWORD /* dwOpcode*/) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 */\* dwOpcode \*/*  
 Réservé.  
  
##  <a name="parsecommandline"></a>  CAtlServiceModuleT::ParseCommandLine  
 Analyse de la ligne de commande et effectue l’inscription si nécessaire.  
  
```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `lpCmdLine`  
 Ligne de commande.  
  
 `pnRetCode`  
 HRESULT correspondant à l’enregistrement (si elle a eu lieu).  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne true en cas de réussite, ou false si le fichier RGS fourni dans la ligne de commande n’a pas pu être enregistré.  
  
### <a name="remarks"></a>Notes  
 Analyse de la ligne de commande et inscrit ou annule l’enregistrement du fichier RGS fourni si nécessaire. Cette méthode appelle [CAtlExeModuleT::ParseCommandLine](../../atl/reference/catlexemodulet-class.md#parsecommandline) pour rechercher les **/RegServer** et **/UnregServer**. Ajout de l’argument **- / Service** inscrira le service.  
  
##  <a name="premessageloop"></a>  CAtlServiceModuleT::PreMessageLoop  
 Cette méthode est appelée immédiatement avant d’entrer dans la boucle de message.  
  
```
HRESULT PreMessageLoop(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `nShowCmd`  
 Ce paramètre est passé à [CAtlExeModuleT::PreMessageLoop](../../atl/reference/catlexemodulet-class.md#premessageloop).  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Substituez cette méthode pour ajouter le code d’initialisation personnalisé pour le Service.  
  
##  <a name="registerappid"></a>  CAtlServiceModuleT::RegisterAppId  
 Inscrit le service dans le Registre.  
  
```
inline HRESULT RegisterAppId(bool bService = false) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 *bService*  
 Doit être true pour inscrire en tant que service.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
##  <a name="run"></a>  CAtlServiceModuleT::Run  
 Exécute le service.  
  
```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `nShowCmd`  
 Spécifie la façon dont la fenêtre doit être affiché. Ce paramètre peut être une des valeurs présentées dans le [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) section. La valeur par défaut est SW_HIDE.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Après avoir été appelé, **exécuter** appelle [CAtlServiceModuleT::PreMessageLoop](#premessageloop), [CAtlExeModuleT::RunMessageLoop](../../atl/reference/catlexemodulet-class.md#runmessageloop), et [CAtlExeModuleT :: PostMessageLoop](../../atl/reference/catlexemodulet-class.md#postmessageloop).  
  
##  <a name="servicemain"></a>  CAtlServiceModuleT::ServiceMain  
 Cette méthode est appelée par le Gestionnaire de contrôle de Service.  
  
```
void ServiceMain(DWORD dwArgc, LPTSTR* lpszArgv) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 *dwArgc*  
 L’argument argc.  
  
 *lpszArgv*  
 L’argument argv.  
  
### <a name="remarks"></a>Notes  
 Les appels du Gestionnaire de contrôle des services (SCM) `ServiceMain` lorsque vous ouvrez l’application Services dans le panneau de configuration, sélectionnez le service et cliquez sur Démarrer.  
  
 Après le SCM appelle `ServiceMain`, un service doit donner au SCM une fonction gestionnaire. Cette fonction permet au SCM obtenir l’état du service et de transférer des instructions spécifiques (par exemple, la mise en pause ou l’arrêt). Par la suite, [CAtlServiceModuleT::Run](#run) est appelée pour effectuer le travail principal du service. **Exécutez** continue à s’exécuter jusqu'à ce que le service est arrêté.  
  
##  <a name="setservicestatus"></a>  CAtlServiceModuleT::SetServiceStatus  
 Cette méthode met à jour l’état du service.  
  
```
void SetServiceStatus(DWORD dwState) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `dwState`  
 Le nouvel état. Consultez [SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241) pour les valeurs possibles.  
  
### <a name="remarks"></a>Notes  
 Met à jour les informations d’état du Gestionnaire de contrôle de Service pour le service. Elle est appelée par [CAtlServiceModuleT::Run](#run), [CAtlServiceModuleT::ServiceMain](#servicemain) et d’autres méthodes de gestionnaire. L’état est également stocké dans la variable membre [CAtlServiceModuleT::m_status](#m_status).  
  
##  <a name="start"></a>  CAtlServiceModuleT::Start  
 Appelé par `CAtlServiceModuleT::WinMain` lorsque le service démarre.  
  
```
HRESULT Start(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `nShowCmd`  
 Spécifie la façon dont la fenêtre doit être affiché. Ce paramètre peut être une des valeurs présentées dans le [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) section.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Le [CAtlServiceModuleT::WinMain](#winmain) méthode gère l’inscription et installation, ainsi que les tâches impliquées dans la suppression des entrées de Registre et de désinstallation du module. Lorsque le service est exécuté, `WinMain` appelle **Démarrer**.  
  
##  <a name="uninstall"></a>  CAtlServiceModuleT::Uninstall  
 Arrête et supprime le service.  
  
```
BOOL Uninstall() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur TRUE en cas de réussite, FALSE en cas d’échec.  
  
### <a name="remarks"></a>Notes  
 Arrête le service de s’exécuter et le supprime de la base de données du Gestionnaire de contrôle de Service.  
  
##  <a name="unlock"></a>  CAtlServiceModuleT::Unlock  
 Décrémente de nombre de verrous du service.  
  
```
LONG Unlock() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le nombre de verrous, ce qui peut être utile pour les tests de diagnostic et de débogage.  
  
##  <a name="unregisterappid"></a>  CAtlServiceModuleT::UnregisterAppId  
 Supprime le service à partir du Registre.  
  
```
HRESULT UnregisterAppId() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
##  <a name="winmain"></a>  CAtlServiceModuleT::WinMain  
 Cette méthode implémente le code requis pour démarrer le service.  
  
```
int WinMain(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `nShowCmd`  
 Spécifie la façon dont la fenêtre doit être affiché. Ce paramètre peut être une des valeurs présentées dans le [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) section.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur de retour du service.  
  
### <a name="remarks"></a>Notes  
 Cette méthode traite la ligne de commande (avec [CAtlServiceModuleT::ParseCommandLine](#parsecommandline)), puis démarre le service (à l’aide de [CAtlServiceModuleT::Start](#start)).  
  
## <a name="see-also"></a>Voir aussi  
 [Classe de CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)
