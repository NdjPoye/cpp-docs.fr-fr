---
title: Classe de CAtlServiceModuleT | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c8fcadca667b618d9e5f112d7910c8e6e6f6c65d
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="catlservicemodulet-class"></a>Classe de CAtlServiceModuleT
Cette classe implémente un service.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
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
|[CAtlServiceModuleT::OnUnknownRequest](#onunknownrequest)|Substituez cette méthode pour gérer les demandes inconnus pour le service|  
|[CAtlServiceModuleT::ParseCommandLine](#parsecommandline)|Analyse de la ligne de commande et effectue l’inscription si nécessaire.|  
|[CAtlServiceModuleT::PreMessageLoop](#premessageloop)|Cette méthode est appelée immédiatement avant d’entrer dans la boucle de message.|  
|[CAtlServiceModuleT::RegisterAppId](#registerappid)|Inscrit le service dans le Registre.|  
|[CAtlServiceModuleT::Run](#run)|Exécute le service.|  
|[CAtlServiceModuleT::ServiceMain](#servicemain)|La méthode appelée par le Gestionnaire de contrôle des services.|  
|[CAtlServiceModuleT::SetServiceStatus](#setservicestatus)|Met à jour l’état du service.|  
|[CAtlServiceModuleT::Start](#start)|Appelé par `CAtlServiceModuleT::WinMain` lorsque le service démarre.|  
|[CAtlServiceModuleT::Uninstall](#uninstall)|Arrête et supprime le service.|  
|[CAtlServiceModuleT::Unlock](#unlock)|Nombre de verrous du service de décrémente.|  
|[CAtlServiceModuleT::UnregisterAppId](#unregisterappid)|Supprime le service à partir du Registre.|  
|[CAtlServiceModuleT::WinMain](#winmain)|Cette méthode implémente le code requis pour exécuter le service.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlServiceModuleT::m_bService](#m_bservice)|Indicateur spécifiant que le programme s’exécute en tant que service.|  
|[CAtlServiceModuleT::m_dwThreadID](#m_dwthreadid)|Variable de membre contenant l’identificateur du thread.|  
|[CAtlServiceModuleT::m_hServiceStatus](#m_hservicestatus)|Variable de membre contenant un handle vers la structure d’information de statut pour le service en cours.|  
|[CAtlServiceModuleT::m_status](#m_status)|Variable de membre le stockage de la structure d’information de statut pour le service en cours.|  
|[CAtlServiceModuleT::m_szServiceName](#m_szservicename)|Le nom du service en cours d’inscription.|  
  
## <a name="remarks"></a>Remarques  
 `CAtlServiceModuleT`, dérivé de [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md), implémente un module Service ATL. `CAtlServiceModuleT`Fournit des méthodes pour le traitement de ligne de commande, installation, l’enregistrement et la suppression. Si les fonctionnalités supplémentaires sont requises, celles-ci et autres méthodes peuvent être substituées.  
  
 Cette classe remplace obsolète [CComModule (classe)](../../atl/reference/ccommodule-class.md) utilisé dans les versions antérieures de l’ATL. Consultez la page [Classes du Module ATL](../../atl/atl-module-classes.md) pour plus de détails.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)  
  
 `CAtlServiceModuleT`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h  
  
##  <a name="catlservicemodulet"></a>CAtlServiceModuleT::CAtlServiceModuleT  
 Constructeur.  
  
```
CAtlServiceModuleT() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Initialise les membres de données et définit l’état du service initial.  
  
##  <a name="handler"></a>CAtlServiceModuleT::Handler  
 La routine du gestionnaire pour le service.  
  
```
void Handler(DWORD dwOpcode) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 *dwOpcode*  
 Un commutateur qui définit l’opération de gestionnaire. Pour plus d’informations, consultez la section Notes.  
  
### <a name="remarks"></a>Remarques  
 Voici le code que le Gestionnaire de contrôle des services (SCM) appelle pour récupérer l’état des instructions de service et le problème comme arrêter ou suspendre. Le SCM passe un code d’opération, indiqué ci-dessous, `Handler` pour indiquer comme le service.  
  
|Code d’opération|Signification|  
|--------------------|-------------|  
|SERVICE_CONTROL_STOP|Arrête le service. Substituez la méthode [CAtlServiceModuleT::OnStop](#onstop) dans atlbase.h pour modifier le comportement.|  
|SERVICE_CONTROL_PAUSE|Utilisateur est implémenté. Substituez la méthode vide [CAtlServiceModuleT::OnPause](#onpause) dans atlbase.h pour interrompre le service.|  
|SERVICE_CONTROL_CONTINUE|Utilisateur est implémenté. Substituez la méthode vide [CAtlServiceModuleT::OnContinue](#oncontinue) dans atlbase.h pour reprendre le service.|  
|SERVICE_CONTROL_INTERROGATE|Utilisateur est implémenté. Substituez la méthode vide [CAtlServiceModuleT::OnInterrogate](#oninterrogate) dans atlbase.h pour interroger le service.|  
|SERVICE_CONTROL_SHUTDOWN|Utilisateur est implémenté. Substituez la méthode vide [CAtlServiceModuleT::OnShutdown](#onshutdown) dans atlbase.h pour arrêter le service.|  
  
 Si le code d’opération n’est pas reconnu, la méthode [CAtlServiceModuleT::OnUnknownRequest](#onunknownrequest) est appelée.  
  
 Un service de généré par ATL par défaut gère uniquement l’instruction d’arrêt. Si le SCM passe l’instruction d’arrêt, le service indique au SCM que le programme est sur le point d’arrêt. Le service appelle ensuite `PostThreadMessage` pour publier un message à lui-même. Cela met fin à la boucle de messages et le service se ferme définitivement.  
  
##  <a name="initializesecurity"></a>CAtlServiceModuleT::InitializeSecurity  
 Fournit la valeur par défaut des paramètres de sécurité pour le service.  
  
```
HRESULT InitializeSecurity() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Dans Visual Studio .NET 2003, cette méthode n’est pas implémentée dans la classe de base. L’Assistant projet Visual Studio inclut cette méthode dans le code généré, mais une erreur de compilation se produit si un projet créé dans une version antérieure de Visual C++ est compilé à l’aide de ATL 7.1. Toute classe qui dérive de `CAtlServiceModuleT` doit implémenter cette méthode dans la classe dérivée.  
  
 Utiliser l’authentification de niveau PKT, niveau d’emprunt d’identité RPC_C_IMP_LEVEL_IDENTIFY et un descripteur de sécurité non null approprié dans l’appel à **CoInitializeSecurity**.  
  
 Pour les projets générés par l’Assistant de service sans attributs, il s’agit de  
  
 [!code-cpp[NVC_ATL_Service n °&1;](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_1.cpp)]  
  
 Pour les projets de service avec attributs, il s’agit dans  
  
 [!code-cpp[NVC_ATL_ServiceAttrib n °&1;](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_2.cpp)]  
  
##  <a name="install"></a>CAtlServiceModuleT::Install  
 Installe et crée le service.  
  
```
BOOL Install() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur TRUE en cas de réussite, FALSE en cas d’échec.  
  
### <a name="remarks"></a>Notes  
 Installe le service dans la base de données du Gestionnaire de contrôle des services (SCM), puis crée l’objet de service. Si le service n’a pas pu être créé, un message s’affiche et la méthode retourne FALSE.  
  
##  <a name="isinstalled"></a>CAtlServiceModuleT::IsInstalled  
 Confirme que le service a été installé.  
  
```
BOOL IsInstalled() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur TRUE si le service est installé, la valeur FALSE.  
  
##  <a name="logevent"></a>CAtlServiceModuleT::LogEvent  
 Écrit dans le journal des événements.  
  
```
void __cdecl LogEvent(LPCTSTR pszFormat, ...) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `pszFormat`  
 Chaîne à écrire dans le journal des événements.  
  
 ...  
 Chaînes supplémentaires facultatives à écrire dans le journal des événements.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode écrit détails et un journal des événements à l’aide de la fonction [ReportEvent](http://msdn.microsoft.com/library/windows/desktop/aa363679). Si aucun service n’est en cours d’exécution, la chaîne est envoyée à la console.  
  
##  <a name="m_bservice"></a>CAtlServiceModuleT::m_bService  
 Indicateur spécifiant que le programme s’exécute en tant que service.  
  
```
BOOL m_bService;
```  
  
### <a name="remarks"></a>Remarques  
 Utilisé pour distinguer un fichier EXE de Service à partir d’un fichier EXE d’Application.  
  
##  <a name="m_dwthreadid"></a>CAtlServiceModuleT::m_dwThreadID  
 Variable de membre contenant l’identificateur du thread du Service.  
  
```
DWORD m_dwThreadID;
```  
  
### <a name="remarks"></a>Remarques  
 Cette variable stocke l’identificateur du thread du thread actuel.  
  
##  <a name="m_hservicestatus"></a>CAtlServiceModuleT::m_hServiceStatus  
 Variable de membre contenant un handle vers la structure d’information de statut pour le service en cours.  
  
```
SERVICE_STATUS_HANDLE m_hServiceStatus;
```  
  
### <a name="remarks"></a>Remarques  
 Le [SERVICE_STATUS](http://msdn.microsoft.com/library/windows/desktop/ms685996) structure contient des informations sur un service.  
  
##  <a name="m_status"></a>CAtlServiceModuleT::m_status  
 Variable de membre le stockage de la structure d’information de statut pour le service en cours.  
  
```
SERVICE_STATUS m_status;
```  
  
### <a name="remarks"></a>Remarques  
 Le [SERVICE_STATUS](http://msdn.microsoft.com/library/windows/desktop/ms685996) structure contient des informations sur un service.  
  
##  <a name="m_szservicename"></a>CAtlServiceModuleT::m_szServiceName  
 Le nom du service en cours d’inscription.  
  
```
TCHAR [256] m_szServiceName;
```  
  
### <a name="remarks"></a>Remarques  
 Chaîne terminée par le caractère null qui stocke le nom du service.  
  
##  <a name="oncontinue"></a>CAtlServiceModuleT::OnContinue  
 Substituez cette méthode pour reprendre le service.  
  
```
void OnContinue() throw();
```  
  
##  <a name="oninterrogate"></a>CAtlServiceModuleT::OnInterrogate  
 Substituez cette méthode pour interroger le service.  
  
```
void OnInterrogate() throw();
```  
  
##  <a name="onpause"></a>CAtlServiceModuleT::OnPause  
 Substituez cette méthode pour suspendre le service.  
  
```
void OnPause() throw();
```  
  
##  <a name="onshutdown"></a>CAtlServiceModuleT::OnShutdown  
 Substituez cette méthode pour arrêter le service.  
  
```
void OnShutdown() throw();
```  
  
##  <a name="onstop"></a>CAtlServiceModuleT::OnStop  
 Substituez cette méthode pour arrêter le service.  
  
```
void OnStop() throw();
```  
  
##  <a name="onunknownrequest"></a>CAtlServiceModuleT::OnUnknownRequest  
 Substituez cette méthode pour gérer les demandes inconnus pour le service.  
  
```
void OnUnknownRequest(DWORD /* dwOpcode*/) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 */\*dwOpcode\*/*  
 Réservé.  
  
##  <a name="parsecommandline"></a>CAtlServiceModuleT::ParseCommandLine  
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
 Retourne la valeur true sur la réussite ou false si le fichier RGS fourni dans la ligne de commande n’a pas pu être enregistré.  
  
### <a name="remarks"></a>Notes  
 Analyse de la ligne de commande et inscrit ou annule l’enregistrement du fichier RGS fourni si nécessaire. Cette méthode appelle [CAtlExeModuleT::ParseCommandLine](../../atl/reference/catlexemodulet-class.md#parsecommandline) pour vérifier les **/RegServer** et **/UnregServer**. Ajout de l’argument **- / Service** inscrira le service.  
  
##  <a name="premessageloop"></a>CAtlServiceModuleT::PreMessageLoop  
 Cette méthode est appelée immédiatement avant d’entrer dans la boucle de message.  
  
```
HRESULT PreMessageLoop(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `nShowCmd`  
 Ce paramètre est passé à [CAtlExeModuleT::PreMessageLoop](../../atl/reference/catlexemodulet-class.md#premessageloop).  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Substituez cette méthode pour ajouter le code d’initialisation personnalisé pour le Service.  
  
##  <a name="registerappid"></a>CAtlServiceModuleT::RegisterAppId  
 Inscrit le service dans le Registre.  
  
```
inline HRESULT RegisterAppId(bool bService = false) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 *bService*  
 Doit être true pour inscrire en tant que service.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
##  <a name="run"></a>CAtlServiceModuleT::Run  
 Exécute le service.  
  
```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `nShowCmd`  
 Spécifie la façon dont la fenêtre doit être affiché. Ce paramètre peut prendre l’une des valeurs présentées dans les [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) section. La valeur par défaut est SW_HIDE.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Après avoir été appelée, **exécuter** appelle [CAtlServiceModuleT::PreMessageLoop](#premessageloop), [CAtlExeModuleT::RunMessageLoop](../../atl/reference/catlexemodulet-class.md#runmessageloop), et [CAtlExeModuleT::PostMessageLoop](../../atl/reference/catlexemodulet-class.md#postmessageloop).  
  
##  <a name="servicemain"></a>CAtlServiceModuleT::ServiceMain  
 Cette méthode est appelée par le Gestionnaire de contrôle des services.  
  
```
void ServiceMain(DWORD dwArgc, LPTSTR* lpszArgv) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 *dwArgc*  
 L’argument argc.  
  
 *lpszArgv*  
 L’argument argv.  
  
### <a name="remarks"></a>Remarques  
 Les appels du Gestionnaire de contrôle des services (SCM) `ServiceMain` lorsque vous ouvrez l’application Services dans le panneau de configuration, sélectionnez le service, puis cliquez sur Démarrer.  
  
 Après le SCM appelle `ServiceMain`, un service doit donner au SCM une fonction gestionnaire. Cette fonction permet au SCM obtenir l’état du service et passer des instructions spécifiques (telles que la suspension ou l’arrêt). Par la suite, [CAtlServiceModuleT::Run](#run) est appelée pour effectuer la tâche principale du service. **Exécutez** continue à s’exécuter jusqu'à ce que le service est arrêté.  
  
##  <a name="setservicestatus"></a>CAtlServiceModuleT::SetServiceStatus  
 Cette méthode met à jour l’état du service.  
  
```
void SetServiceStatus(DWORD dwState) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `dwState`  
 Le nouvel état. Consultez la page [SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241) pour les valeurs possibles.  
  
### <a name="remarks"></a>Remarques  
 Met à jour les informations d’état du Gestionnaire de contrôle de Service pour le service. Elle est appelée par [CAtlServiceModuleT::Run](#run), [CAtlServiceModuleT::ServiceMain](#servicemain) et d’autres méthodes de gestionnaire. L’état est également stockée dans la variable membre [CAtlServiceModuleT::m_status](#m_status).  
  
##  <a name="start"></a>CAtlServiceModuleT::Start  
 Appelé par `CAtlServiceModuleT::WinMain` lorsque le service démarre.  
  
```
HRESULT Start(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `nShowCmd`  
 Spécifie la façon dont la fenêtre doit être affiché. Ce paramètre peut prendre l’une des valeurs présentées dans les [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) section.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Le [CAtlServiceModuleT::WinMain](#winmain) méthode gère l’inscription et installation, ainsi que les tâches impliquées dans la suppression des entrées de Registre et de désinstaller le module. Lorsque le service est exécuté, `WinMain` appelle **Démarrer**.  
  
##  <a name="uninstall"></a>CAtlServiceModuleT::Uninstall  
 Arrête et supprime le service.  
  
```
BOOL Uninstall() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur TRUE en cas de réussite, FALSE en cas d’échec.  
  
### <a name="remarks"></a>Notes  
 Arrête le service et le supprime de la base de données du Gestionnaire de contrôle de Service.  
  
##  <a name="unlock"></a>CAtlServiceModuleT::Unlock  
 Nombre de verrous du service de décrémente.  
  
```
LONG Unlock() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le nombre de verrous, qui peut être utile pour le diagnostic et le débogage.  
  
##  <a name="unregisterappid"></a>CAtlServiceModuleT::UnregisterAppId  
 Supprime le service à partir du Registre.  
  
```
HRESULT UnregisterAppId() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
##  <a name="winmain"></a>CAtlServiceModuleT::WinMain  
 Cette méthode implémente le code requis pour démarrer le service.  
  
```
int WinMain(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `nShowCmd`  
 Spécifie la façon dont la fenêtre doit être affiché. Ce paramètre peut prendre l’une des valeurs présentées dans les [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) section.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur de retour du service.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode traite la ligne de commande (avec [CAtlServiceModuleT::ParseCommandLine](#parsecommandline)), puis démarre le service (à l’aide de [CAtlServiceModuleT::Start](#start)).  
  
## <a name="see-also"></a>Voir aussi  
 [CAtlExeModuleT (classe)](../../atl/reference/catlexemodulet-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)
