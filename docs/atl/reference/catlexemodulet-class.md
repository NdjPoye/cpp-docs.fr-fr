---
title: Classe de CAtlExeModuleT | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlExeModuleT
- ATLBASE/ATL::CAtlExeModuleT
- ATLBASE/ATL::CAtlExeModuleT::CAtlExeModuleT
- ATLBASE/ATL::CAtlExeModuleT::InitializeCom
- ATLBASE/ATL::CAtlExeModuleT::ParseCommandLine
- ATLBASE/ATL::CAtlExeModuleT::PostMessageLoop
- ATLBASE/ATL::CAtlExeModuleT::PreMessageLoop
- ATLBASE/ATL::CAtlExeModuleT::RegisterClassObjects
- ATLBASE/ATL::CAtlExeModuleT::RevokeClassObjects
- ATLBASE/ATL::CAtlExeModuleT::Run
- ATLBASE/ATL::CAtlExeModuleT::RunMessageLoop
- ATLBASE/ATL::CAtlExeModuleT::UninitializeCom
- ATLBASE/ATL::CAtlExeModuleT::Unlock
- ATLBASE/ATL::CAtlExeModuleT::WinMain
- ATLBASE/ATL::CAtlExeModuleT::m_bDelayShutdown
- ATLBASE/ATL::CAtlExeModuleT::m_dwPause
- ATLBASE/ATL::CAtlExeModuleT::m_dwTimeOut
dev_langs:
- C++
helpviewer_keywords:
- CAtlExeModuleT class
ms.assetid: 82245f3d-91d4-44fa-aa86-7cc7fbd758d9
caps.latest.revision: 21
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 24ee6c4dfb13c31377bdd7d4f57a92d4f11ad4b8
ms.lasthandoff: 02/24/2017

---
# <a name="catlexemodulet-class"></a>CAtlExeModuleT (classe)
Cette classe représente le module pour une application.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class T>  
class ATL_NO_VTABLE CAtlExeModuleT : public CAtlModuleT<T>
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Votre classe dérivée de `CAtlExeModuleT`.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlExeModuleT::CAtlExeModuleT](#catlexemodulet)|Constructeur.|  
|[CAtlExeModuleT :: ~ CAtlExeModuleT](#dtor)|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlExeModuleT::InitializeCom](#initializecom)|Initialise com|  
|[CAtlExeModuleT::ParseCommandLine](#parsecommandline)|Analyse de la ligne de commande et effectue l’inscription si nécessaire.|  
|[CAtlExeModuleT::PostMessageLoop](#postmessageloop)|Cette méthode est appelée immédiatement après que la boucle de message se ferme.|  
|[CAtlExeModuleT::PreMessageLoop](#premessageloop)|Cette méthode est appelée immédiatement avant d’entrer dans la boucle de message.|  
|[CAtlExeModuleT::RegisterClassObjects](#registerclassobjects)|Enregistre l’objet de classe.|  
|[CAtlExeModuleT::RevokeClassObjects](#revokeclassobjects)|Révoque l’objet de classe.|  
|[CAtlExeModuleT::Run](#run)|Cette méthode exécute le code dans le module EXE à initialiser, exécuter la boucle de messages et de nettoyer.|  
|[CAtlExeModuleT::RunMessageLoop](#runmessageloop)|Cette méthode exécute la boucle de message.|  
|[CAtlExeModuleT::UninitializeCom](#uninitializecom)|N’initialise pas COM.|  
|[CAtlExeModuleT::Unlock](#unlock)|Nombre de verrous du module de décrémente.|  
|[CAtlExeModuleT::WinMain](#winmain)|Cette méthode implémente le code requis pour exécuter un fichier EXE.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlExeModuleT::m_bDelayShutdown](#m_bdelayshutdown)|Indicateur signalant qu’il doit y avoir un délai d’arrêt du module.|  
|[CAtlExeModuleT::m_dwPause](#m_dwpause)|Une valeur de pause permet de vous assurer que tous les objets sont libérées avant l’arrêt.|  
|[CAtlExeModuleT::m_dwTimeOut](#m_dwtimeout)|Une valeur de délai d’expiration utilisée pour différer le déchargement du module.|  
  
## <a name="remarks"></a>Remarques  
 `CAtlExeModuleT`représente le module pour une application (EXE) et contient le code qui prend en charge la création d’un fichier EXE, traitement de la ligne de commande, l’inscription d’objets de classe, exécuter une boucle de message et le nettoyage à la sortie.  
  
 Cette classe est conçue pour améliorer les performances lorsque les objets COM du serveur EXE sont continuellement créés et détruits. Après le dernier objet COM est libéré, le fichier EXE attend pendant une durée spécifiée par la [CAtlExeModuleT::m_dwTimeOut](#m_dwtimeout) membre de données. S’il n’existe aucune activité pendant cette période (autrement dit, les objets COM sont créés), le processus d’arrêt est lancé.  
  
 Le [CAtlExeModuleT::m_bDelayShutdown](#m_bdelayshutdown) membre de données est un indicateur permet de déterminer si le fichier exécutable doit utiliser le mécanisme défini ci-dessus. Si elle est définie sur false, le module s’arrêter immédiatement.  
  
 Pour plus d’informations sur les modules dans ATL, consultez [Classes du Module ATL](../../atl/atl-module-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  

  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CAtlExeModuleT`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h  
  
##  <a name="catlexemodulet"></a>CAtlExeModuleT::CAtlExeModuleT  
 Constructeur.  
  
```
CAtlExeModuleT() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Si le module EXE n’a pas pu être initialisé, WinMain renvoie immédiatement sans traitement supplémentaire.  
  
##  <a name="dtor"></a>CAtlExeModuleT :: ~ CAtlExeModuleT  
 Destructeur.  
  
```
~CAtlExeModuleT() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Libère toutes les ressources attribuées.  
  
##  <a name="initializecom"></a>CAtlExeModuleT::InitializeCom  
 Initialise com  
  
```
static HRESULT InitializeCom() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette méthode est appelée à partir du constructeur et peut être remplacée pour initialiser COM d’une manière différente de l’implémentation par défaut. L’implémentation par défaut appelle soit **CoInitializeEx (NULL, COINIT_MULTITHREADED)** ou **CoInitialize(NULL)** selon la configuration du projet.  
  
 Normalement la substitution de cette méthode requiert la substitution de [CAtlExeModuleT::UninitializeCom](#uninitializecom).  
  
##  <a name="m_bdelayshutdown"></a>CAtlExeModuleT::m_bDelayShutdown  
 Indicateur signalant qu’il doit y avoir un délai d’arrêt du module.  
  
```
bool m_bDelayShutdown;
```  
  
### <a name="remarks"></a>Remarques  
 Consultez le [CAtlExeModuleT présentation](../../atl/reference/catlexemodulet-class.md) pour plus d’informations.  
  
##  <a name="m_dwpause"></a>CAtlExeModuleT::m_dwPause  
 Une valeur de pause permet de vérifier que tous les objets sont mis en avant l’arrêt.  
  
```
DWORD m_dwPause;
```  
  
### <a name="remarks"></a>Remarques  
 Modifiez cette valeur après avoir appelé [CAtlExeModuleT::InitializeCom](#initializecom) pour définir le nombre de millisecondes, utilisé en tant que la valeur de pause pour arrêter le serveur. La valeur par défaut est 1 000 millisecondes.  
  
##  <a name="m_dwtimeout"></a>CAtlExeModuleT::m_dwTimeOut  
 Une valeur de délai d’expiration utilisée pour différer le déchargement du module.  
  
```
DWORD m_dwTimeOut;
```  
  
### <a name="remarks"></a>Remarques  
 Modifiez cette valeur après avoir appelé [CAtlExeModuleT::InitializeCom](#initializecom) pour définir le nombre de millisecondes, utilisé en tant que la valeur de délai d’attente pour l’arrêt du serveur. La valeur par défaut est 5 000 millisecondes. Consultez le [CAtlExeModuleT présentation](../../atl/reference/catlexemodulet-class.md) pour plus de détails.  
  
##  <a name="parsecommandline"></a>CAtlExeModuleT::ParseCommandLine  
 Analyse de la ligne de commande et effectue l’inscription si nécessaire.  
  
```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `lpCmdLine`  
 La ligne de commande passés à l’application.  
  
 `pnRetCode`  
 HRESULT correspondant à l’enregistrement (si elle a eu lieu).  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne true si l’application doit continuer à s’exécuter, sinon false.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode est appelée à partir de [CAtlExeModuleT::WinMain](#winmain) et peut être substituée pour gérer les commutateurs de ligne de commande. L’implémentation par défaut recherche **/RegServer** et **/UnRegServer** des arguments de ligne de commande et effectue l’inscription ou l’annulation d’inscription.  
  
##  <a name="postmessageloop"></a>CAtlExeModuleT::PostMessageLoop  
 Cette méthode est appelée immédiatement après que la boucle de message se ferme.  
  
```
HRESULT PostMessageLoop() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Substituez cette méthode pour effectuer un nettoyage de l’application personnalisée. L’implémentation par défaut appelle [CAtlExeModuleT::RevokeClassObjects](#revokeclassobjects).  
  
##  <a name="premessageloop"></a>CAtlExeModuleT::PreMessageLoop  
 Cette méthode est appelée immédiatement avant d’entrer dans la boucle de message.  
  
```
HRESULT PreMessageLoop(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `nShowCmd`  
 La valeur passée comme le `nShowCmd` paramètre WinMain.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Substituez cette méthode pour ajouter du code d’initialisation personnalisée pour l’application. L’implémentation par défaut enregistre les objets de classe.  
  
##  <a name="registerclassobjects"></a>CAtlExeModuleT::RegisterClassObjects  
 Enregistre l’objet de classe avec OLE afin d’autres applications peuvent se connecter à celui-ci.  
  
```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 *dwClsContext*  
 Spécifie le contexte dans lequel l’objet de classe doit être exécutée. Les valeurs possibles sont CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER ou CLSCTX_LOCAL_SERVER.  
  
 `dwFlags`  
 Détermine les types de connexion à l’objet de classe. Les valeurs possibles sont REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE ou REGCLS_MULTI_SEPARATE.  
  
### <a name="return-value"></a>Valeur de retour  
 Sur la réussite, S_FALSE s’il n’y a aucune classe pour inscrire ou une erreur HRESULT en cas d’échec, retourne S_OK.  
  
##  <a name="revokeclassobjects"></a>CAtlExeModuleT::RevokeClassObjects  
 Supprime l’objet de classe.  
  
```
HRESULT RevokeClassObjects() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Sur la réussite, S_FALSE s’il n’y a aucune classe pour inscrire ou une erreur HRESULT en cas d’échec, retourne S_OK.  
  
##  <a name="run"></a>CAtlExeModuleT::Run  
 Cette méthode exécute le code dans le module EXE à initialiser, exécuter la boucle de messages et de nettoyer.  
  
```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `nShowCmd`  
 Spécifie la façon dont la fenêtre doit être affiché. Ce paramètre peut prendre l’une des valeurs présentées dans les [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) section. La valeur par défaut est SW_HIDE.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode peut être substituée. Toutefois, dans la pratique est-il préférable de substituer [CAtlExeModuleT::PreMessageLoop](#premessageloop), [CAtlExeModuleT::RunMessageLoop](#runmessageloop), ou [CAtlExeModuleT::PostMessageLoop](#postmessageloop) à la place.  
  
##  <a name="runmessageloop"></a>CAtlExeModuleT::RunMessageLoop  
 Cette méthode exécute la boucle de message.  
  
```
void RunMessageLoop() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Cette méthode peut être substituée pour modifier le comportement de la boucle de message.  
  
##  <a name="uninitializecom"></a>CAtlExeModuleT::UninitializeCom  
 N’initialise pas COM.  
  
```
static void UninitializeCom() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Par défaut cette méthode appelle simplement [CoUninitialize](http://msdn.microsoft.com/library/windows/desktop/ms688715) et est appelé à partir du destructeur. Substituez cette méthode si vous substituez [CAtlExeModuleT::InitializeCom](#initializecom).  
  
##  <a name="unlock"></a>CAtlExeModuleT::Unlock  
 Nombre de verrous du module de décrémente.  
  
```
LONG Unlock() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne une valeur qui peut être utile pour les tests de diagnostic ou de test.  
  
##  <a name="winmain"></a>CAtlExeModuleT::WinMain  
 Cette méthode implémente le code requis pour exécuter un fichier EXE.  
  
```
int WinMain(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `nShowCmd`  
 Spécifie la façon dont la fenêtre doit être affiché. Ce paramètre peut prendre l’une des valeurs présentées dans les [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) section.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur de retour de l’exécutable.  
  
### <a name="remarks"></a>Notes  
 Cette méthode peut être substituée. Si vous la substituez [CAtlExeModuleT::PreMessageLoop](#premessageloop), [CAtlExeModuleT::PostMessageLoop](#postmessageloop), ou [CAtlExeModuleT::RunMessageLoop](#runmessageloop) ne fournit pas suffisamment de souplesse, il est possible de remplacer le `WinMain` fonction à l’aide de cette méthode.  
  
## <a name="see-also"></a>Voir aussi  
 [ATLDuck, exemple](../../visual-cpp-samples.md)   
 [CAtlModuleT (classe)](../../atl/reference/catlmodulet-class.md)   
 [CAtlDllModuleT (classe)](../../atl/reference/catldllmodulet-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

