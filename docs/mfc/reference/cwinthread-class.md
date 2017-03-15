---
title: CWinThread (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinThread
dev_langs:
- C++
helpviewer_keywords:
- worker threads
- threading [MFC], safety
- CWinThread class
- threading [MFC], creating threads
ms.assetid: 10cdc294-4057-4e76-ac7c-a8967a89af0b
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 866e847f9c1d73d6f9882e50b1274fbad9e21a39
ms.lasthandoff: 02/24/2017

---
# <a name="cwinthread-class"></a>CWinThread (classe)
Représente un thread d'exécution dans une application.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CWinThread : public CCmdTarget  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CWinThread::CWinThread](#cwinthread)|Construit un objet `CWinThread`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CWinThread::CreateThread](#createthread)|Démarre l’exécution d’une `CWinThread` objet.|  
|[CWinThread::ExitInstance](#exitinstance)|Substituez pour nettoyer votre thread se termine.|  
|[CWinThread::GetMainWnd](#getmainwnd)|Récupère un pointeur vers la fenêtre principale du thread.|  
|[CWinThread::GetThreadPriority](#getthreadpriority)|Obtient la priorité du thread actuel.|  
|[CWinThread::InitInstance](#initinstance)|Substituez pour effectuer une initialisation instance thread.|  
|[CWinThread::IsIdleMessage](#isidlemessage)|Vérifie les messages spéciaux.|  
|[CWinThread::OnIdle](#onidle)|Substituez pour effectuer le traitement des temps d’inactivité spécifique au thread.|  
|[CWinThread::PostThreadMessage](#postthreadmessage)|Publie un message à un autre `CWinThread` objet.|  
|[CWinThread::PreTranslateMessage](#pretranslatemessage)|Filtre les messages avant leur distribution aux fonctions Windows [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) et [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934).|  
|[CWinThread::ProcessMessageFilter](#processmessagefilter)|Intercepte certains messages avant qu’ils atteignent l’application.|  
|[CWinThread::ProcessWndProcException](#processwndprocexception)|Intercepte toutes les exceptions non gérées levées par message du thread ainsi que les gestionnaires de commandes.|  
|[CWinThread::PumpMessage](#pumpmessage)|Contient la boucle de messages du thread.|  
|[CWinThread::ResumeThread](#resumethread)|Décrémente une du thread compteur de suspension.|  
|[CWinThread::Run](#run)|Fonction de contrôle des threads avec une pompe de messages. Remplacement pour personnaliser la boucle de message par défaut.|  
|[CWinThread::SetThreadPriority](#setthreadpriority)|Définit la priorité du thread actuel.|  
|[CWinThread::SuspendThread](#suspendthread)|Incrémente un du thread compteur de suspension.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CWinThread::operator descripteur](#operator_handle)|Récupère le handle de la `CWinThread` objet.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CWinThread::m_bAutoDelete](#m_bautodelete)|Spécifie s’il faut détruire l’objet à l’arrêt du thread.|  
|[CWinThread::m_hThread](#m_hthread)|Handle du thread actuel.|  
|[CWinThread::m_nThreadID](#m_nthreadid)|ID du thread actuel.|  
|[CWinThread::m_pActiveWnd](#m_pactivewnd)|Pointeur vers la fenêtre principale de l’application de conteneur lorsqu’un serveur OLE est actif sur place.|  
|[CWinThread::m_pMainWnd](#m_pmainwnd)|Contient un pointeur vers la fenêtre principale de l’application.|  
  
## <a name="remarks"></a>Remarques  
 Le thread d’exécution principal est généralement fournie par un objet dérivé `CWinApp`; `CWinApp` est dérivée de `CWinThread`. Autres `CWinThread` objets autorisant plusieurs threads dans une application donnée.  
  
 Il existe deux types généraux de threads qui `CWinThread` prend en charge : threads de travail et de threads d’interface utilisateur. Threads de travail ont sans pompe de messages : par exemple, un thread qui effectue des calculs en arrière-plan dans une application de feuille de calcul. Threads d’interface utilisateur ont une pompe de messages et traitement les messages reçus à partir du système. [CWinApp](../../mfc/reference/cwinapp-class.md) et classes dérivées sont des exemples de threads d’interface utilisateur. Autres threads d’interface utilisateur peuvent également être dérivés directement `CWinThread`.  
  
 Objets de la classe `CWinThread` existent généralement pendant la durée du thread. Si vous souhaitez modifier ce comportement, affectez [m_bAutoDelete](#m_bautodelete) à **FALSE**.  
  
 La `CWinThread` classe est nécessaire pour rendre votre code et MFC complètement thread-safe. Données locales de thread utilisées par l’infrastructure pour mettre à jour les informations spécifiques au thread gérées par `CWinThread` objets. En raison de cette dépendance sur `CWinThread` pour gérer les données locales de thread, un thread qui utilise MFC doit être créé par MFC. Par exemple, un thread créé par la fonction d’exécution [_beginthread, _beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) ne pouvez pas utiliser les API de MFC.  
  
 Pour créer un thread, appelez [AfxBeginThread](application-information-and-management.md#afxbeginthread). Il existe deux formes, selon que vous souhaitez un thread de travail ou d’interface utilisateur. Si vous souhaitez un thread d’interface utilisateur, passez à `AfxBeginThread` un pointeur vers le `CRuntimeClass` de vos `CWinThread`-classe dérivée. Si vous souhaitez créer un thread de travail, passez à `AfxBeginThread` un pointeur vers la fonction de contrôle et le paramètre pour la fonction de contrôle. Pour les threads de travail et les threads d’interface utilisateur, vous pouvez spécifier des paramètres facultatifs qui modifient la priorité, la taille de pile, indicateurs de création et les attributs de sécurité. `AfxBeginThread`Retourne un pointeur vers votre nouvelle `CWinThread` objet.  
  
 Au lieu d’appeler `AfxBeginThread`, vous pouvez construire un `CWinThread`-dérivés d’objet, puis appelez `CreateThread`. Cette méthode de construction en deux étapes est utile si vous souhaitez réutiliser la `CWinThread` objet entre la création successive et arrêts d’exécutions de thread.  
  
 Pour plus d’informations sur `CWinThread`, consultez les articles [Multithreading à l’aide de C++ et MFC](../../parallel/multithreading-with-cpp-and-mfc.md), [Multithreading : création de Threads d’Interface utilisateur](../../parallel/multithreading-creating-user-interface-threads.md), [Multithreading : création de Threads de travail](../../parallel/multithreading-creating-worker-threads.md), et [Multithreading : comment utiliser les Classes de synchronisation](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CWinThread`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h  
  
##  <a name="a-namecreatethreada--cwinthreadcreatethread"></a><a name="createthread"></a>CWinThread::CreateThread  
 Crée un thread s’exécute dans l’espace d’adressage du processus appelant.  
  
```  
BOOL CreateThread(
    DWORD dwCreateFlags = 0,  
    UINT nStackSize = 0,  
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwCreateFlags`  
 Spécifie un indicateur supplémentaire qui contrôle la création du thread. Cet indicateur peut contenir une des deux valeurs :  
  
- **CREATE_SUSPENDED** démarrer le thread avec un compteur de suspension d’un. Utilisez **CREATE_SUSPENDED** si vous souhaitez initialiser les données membres de la `CWinThread` de l’objet, tel que [m_bAutoDelete](#m_bautodelete) ou tous les membres de votre classe dérivée, avant le démarrage du thread en cours d’exécution. Une fois votre initialisation est terminée, utilisez la [CWinThread::ResumeThread](#resumethread) pour démarrer le thread en cours d’exécution. Le thread s’exécute pas tant que `CWinThread::ResumeThread` est appelée.  
  
- **0** démarrer le thread immédiatement après sa création.  
  
 `nStackSize`  
 Spécifie la taille en octets de la pile pour le nouveau thread. Si **0**, la taille de pile par défaut est la même taille que celle du thread principal du processus.  
  
 `lpSecurityAttrs`  
 Pointe vers une [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) structure qui spécifie les attributs de sécurité pour le thread.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le thread est créé avec succès ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Utilisez `AfxBeginThread` pour créer un objet thread et l’exécuter en une seule étape. Utilisez `CreateThread` si vous souhaitez réutiliser l’objet thread entre successive création et l’arrêt d’exécution du thread.  
  
##  <a name="a-namecwinthreada--cwinthreadcwinthread"></a><a name="cwinthread"></a>CWinThread::CWinThread  
 Construit un objet `CWinThread`.  
  
```  
CWinThread();
```  
  
### <a name="remarks"></a>Remarques  
 Pour commencer l’exécution du thread, appelez la [CreateThread](#createthread) fonction membre. Vous créerez en général des threads en appelant [AfxBeginThread](http://msdn.microsoft.com/library/e9e8684d-24f7-4599-8fdf-1f4f560a753b), qui appelle ce constructeur et `CreateThread`.  
  
##  <a name="a-nameexitinstancea--cwinthreadexitinstance"></a><a name="exitinstance"></a>CWinThread::ExitInstance  
 Appelé par l’infrastructure à partir de rarement substituée [exécuter](#run) fonction membre pour quitter cette instance du thread, ou si un appel à [InitInstance](#initinstance) échoue.  
  
```  
virtual int ExitInstance();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Code de sortie du thread ; 0 n’indique aucune erreur, et les valeurs supérieures à 0 indiquent une erreur. Cette valeur peut être récupérée en appelant [GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190).  
  
### <a name="remarks"></a>Remarques  
 N’appelez pas cette fonction membre à partir de n’importe quel emplacement, mais dans le **exécuter** fonction membre. Cette fonction membre est utilisée uniquement dans les threads d’interface utilisateur.  
  
 L’implémentation par défaut de cette fonction supprime le `CWinThread` si l’objet [m_bAutoDelete](#m_bautodelete) est **TRUE**. Remplacez cette fonction si vous souhaitez effectuer un nettoyage supplémentaire quand votre thread se termine. Votre implémentation de `ExitInstance` doit appeler la version de la classe de base après l’exécution de votre code.  
  
##  <a name="a-namegetmainwnda--cwinthreadgetmainwnd"></a><a name="getmainwnd"></a>CWinThread::GetMainWnd  
 Si votre application est un serveur OLE, appelez cette fonction pour récupérer un pointeur vers la fenêtre principale active de l’application au lieu de faire référence directement à le `m_pMainWnd` membre de l’objet application.  
  
```  
virtual CWnd* GetMainWnd();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Cette fonction retourne un pointeur vers un des deux types de fenêtres. Si votre thread fait partie d’un serveur OLE et dispose d’un objet qui est actif sur place à l’intérieur d’un conteneur, cette fonction retourne le [CWinApp::m_pActiveWnd](../../mfc/reference/cwinapp-class.md#m_pactivewnd) membre de données de la `CWinThread` objet.  
  
 S’il n’existe aucun objet qui est actif sur place dans un conteneur ou votre application n’est pas un serveur OLE, cette fonction retourne le [m_pMainWnd](#m_pmainwnd) membre de données de l’objet thread.  
  
### <a name="remarks"></a>Remarques  
 Pour les threads d’interface utilisateur, cela équivaut à faire référence directement à le `m_pActiveWnd` membre de votre objet application.  
  
 Si votre application n’est pas un serveur OLE, puis appeler cette fonction est équivalente à la référence directement à le `m_pMainWnd` membre de votre objet application.  
  
 Remplacez cette fonction pour modifier le comportement par défaut.  
  
##  <a name="a-namegetthreadprioritya--cwinthreadgetthreadpriority"></a><a name="getthreadpriority"></a>CWinThread::GetThreadPriority  
 Obtient le niveau de priorité de thread en cours de ce thread.  
  
```  
int GetThreadPriority();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Niveau de la priorité de thread en cours dans sa classe de priorité. La valeur retournée sera un des éléments suivants, répertoriés à partir de la priorité la plus élevée à la plus faible :  
  
- **THREAD_PRIORITY_TIME_CRITICAL**  
  
- **THREAD_PRIORITY_HIGHEST**  
  
- **THREAD_PRIORITY_ABOVE_NORMAL**  
  
- **THREAD_PRIORITY_NORMAL**  
  
- **THREAD_PRIORITY_BELOW_NORMAL**  
  
- **NIVEAU DE PRIORITÉ**  
  
- **THREAD_PRIORITY_IDLE**  
  
 Pour plus d’informations sur ces priorités, consultez [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameinitinstancea--cwinthreadinitinstance"></a><a name="initinstance"></a>CWinThread::InitInstance  
 `InitInstance`doit être substitué pour initialiser chaque nouvelle instance d’un thread d’interface utilisateur.  
  
```  
virtual BOOL InitInstance();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’initialisation aboutit ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 En règle générale, vous substituez `InitInstance` pour effectuer les tâches qui doivent être effectuées lorsque vous créez un thread.  
  
 Cette fonction membre est utilisée uniquement dans les threads d’interface utilisateur. Exécuter l’initialisation de threads de travail dans la fonction de contrôle passée à [AfxBeginThread](application-information-and-management.md#afxbeginthread).  
  
##  <a name="a-nameisidlemessagea--cwinthreadisidlemessage"></a><a name="isidlemessage"></a>CWinThread::IsIdleMessage  
 Remplacez cette fonction pour conserver **OnIdle** d’être appelée après la génération des messages spécifiques.  
  
```  
virtual BOOL IsIdleMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Paramètres  
 `pMsg`  
 Pointe vers le message actuel en cours de traitement.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si `OnIdle` doit être appelée après le traitement de message, sinon 0.  
  
### <a name="remarks"></a>Remarques  
 L’implémentation par défaut n’appelle pas **OnIdle** après les messages de souris redondants et des messages générés par clignote signes.  
  
 Si une application a créé un minuteur court, **OnIdle** sera appelé fréquemment, à l’origine des problèmes de performances. Pour améliorer les performances d’une telle application, substituez `IsIdleMessage` dans l’application `CWinApp`-classe dont vous recherchez dérivée `WM_TIMER` messages comme suit :  
  
 [!code-cpp[NVC_MFCDocView&#189;](../../mfc/codesnippet/cpp/cwinthread-class_1.cpp)]  
  
 Gestion des `WM_TIMER` de cette façon améliore les performances des applications qui utilisent des minuteries courts.  
  
##  <a name="a-namembautodeletea--cwinthreadmbautodelete"></a><a name="m_bautodelete"></a>CWinThread::m_bAutoDelete  
 Spécifie si le `CWinThread` objet doit être supprimé automatiquement à l’arrêt du thread.  
  
```  
BOOL m_bAutoDelete;  
```  
  
### <a name="remarks"></a>Remarques  
 Le `m_bAutoDelete` membre de données est une variable publique de type **BOOL**.  
  
 La valeur de `m_bAutoDelete` n’affecte pas la façon dont le handle du thread sous-jacent est fermé. Le handle du thread est fermé toujours lorsque le `CWinThread` est détruit.  
  
##  <a name="a-namemhthreada--cwinthreadmhthread"></a><a name="m_hthread"></a>CWinThread::m_hThread  
 Pointeur vers le thread associé à ce `CWinThread`.  
  
```  
HANDLE m_hThread;  
```  
  
### <a name="remarks"></a>Notes  
 Le `m_hThread` membre de données est une variable publique de type `HANDLE`. Il est uniquement valide si sous-jacente thread actuellement existe.  
  
##  <a name="a-namemnthreadida--cwinthreadmnthreadid"></a><a name="m_nthreadid"></a>CWinThread::m_nThreadID  
 ID du thread associé à ce `CWinThread`.  
  
```  
DWORD m_nThreadID;  
```  
  
### <a name="remarks"></a>Remarques  
 Le **m_nThreadID** membre de données est une variable publique de type `DWORD`. Il est uniquement valide si sous-jacente thread actuellement existe.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [AfxGetThread](application-information-and-management.md#afxgetthread).  
  
##  <a name="a-namempactivewnda--cwinthreadmpactivewnd"></a><a name="m_pactivewnd"></a>CWinThread::m_pActiveWnd  
 Utilisez ce membre de données pour stocker un pointeur vers l’objet de la fenêtre active de votre thread.  
  
```  
CWnd* m_pActiveWnd;  
```  
  
### <a name="remarks"></a>Remarques  
 La bibliothèque Microsoft Foundation Class se terminera automatiquement votre thread lorsque la fenêtre référencée par `m_pActiveWnd` est fermé. Si ce thread est le thread principal d’une application, l’application prend également fin. Si ce membre de données est **NULL**, la fenêtre active de l’application `CWinApp` objet est hérité. `m_pActiveWnd`est une variable publique de type **CWnd\***.  
  
 En général, vous définissez cette variable membre lorsque vous substituez `InitInstance`. Dans un thread de travail, la valeur de ce membre de données est héritée de son thread parent.  
  
##  <a name="a-namempmainwnda--cwinthreadmpmainwnd"></a><a name="m_pmainwnd"></a>CWinThread::m_pMainWnd  
 Utilisez ce membre de données pour stocker un pointeur vers l’objet de fenêtre principale de votre thread.  
  
```  
CWnd* m_pMainWnd;  
```  
  
### <a name="remarks"></a>Remarques  
 La bibliothèque Microsoft Foundation Class se terminera automatiquement votre thread lorsque la fenêtre référencée par `m_pMainWnd` est fermé. Si ce thread est le thread principal d’une application, l’application prend également fin. Si ce membre de données est **NULL**, la fenêtre principale de l’application `CWinApp` objet sera utilisé pour déterminer quand arrêter le thread. `m_pMainWnd`est une variable publique de type **CWnd\***.  
  
 En général, vous définissez cette variable membre lorsque vous substituez `InitInstance`. Dans un thread de travail, la valeur de ce membre de données est héritée de son thread parent.  
  
##  <a name="a-nameonidlea--cwinthreadonidle"></a><a name="onidle"></a>CWinThread::OnIdle  
 Remplacez cette fonction membre pour effectuer le traitement des temps d’inactivité.  
  
```  
virtual BOOL OnIdle(LONG lCount);
```  
  
### <a name="parameters"></a>Paramètres  
 `lCount`  
 Un compteur incrémenté chaque fois que `OnIdle` est appelé lorsque la file d’attente de messages du thread est vide. Ce compteur est réinitialisé à 0 à chaque fois qu’un nouveau message est traité. Vous pouvez utiliser la `lCount` paramètre pour déterminer la durée relative le thread a été inactif sans le traitement d’un message.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro pour recevoir plus le temps de traitement inactif ; 0 si non plus de temps de traitement inactif.  
  
### <a name="remarks"></a>Remarques  
 `OnIdle`est appelée dans la boucle de message par défaut lors de la file d’attente de messages du thread est vide. Utilisez votre remplacement pour appeler votre propre expérience de tâches du Gestionnaire d’inactivité.  
  
 `OnIdle`Renvoie 0 pour indiquer qu’aucun temps de traitement inactif supplémentaire n’est nécessaire. Le `lCount` paramètre est incrémenté chaque fois que `OnIdle` est appelé lorsque la file d’attente est vide et qu’il est réinitialisé à 0, chaque fois qu’un nouveau message est traité. Vous pouvez appeler vos routines d’inactivité différents en fonction de ce nombre.  
  
 L’implémentation par défaut de cette fonction membre libère des objets temporaires et des bibliothèques de liens dynamiques inutilisées de la mémoire.  
  
 Cette fonction membre est utilisée uniquement dans les threads d’interface utilisateur.  
  
 Étant donné que l’application ne peut pas traiter les messages jusqu'à ce que `OnIdle` retourne, n’effectuez pas de tâches de longue durée dans cette fonction.  
  
##  <a name="a-nameoperatorhandlea--cwinthreadoperator-handle"></a><a name="operator_handle"></a>CWinThread::operator descripteur  
 Récupère le handle de la `CWinThread` objet.  
  
```  
operator HANDLE() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Si l’opération réussit, le handle de l’objet thread. dans le cas contraire, **NULL**.  
  
### <a name="remarks"></a>Remarques  
 Utilisez la poignée pour appeler directement les API Windows.  
  
##  <a name="a-namepostthreadmessagea--cwinthreadpostthreadmessage"></a><a name="postthreadmessage"></a>CWinThread::PostThreadMessage  
 Appelé pour envoyer un message défini par l’utilisateur à un autre `CWinThread` objet.  
  
```  
BOOL PostThreadMessage(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Paramètres  
 `message`  
 ID du message défini par l’utilisateur.  
  
 `wParam`  
 Premier paramètre de message.  
  
 `lParam`  
 Deuxième paramètre de message.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Le message publié est mappé vers le Gestionnaire de message approprié par la macro de mappage de message `ON_THREAD_MESSAGE`.  
  
> [!NOTE]
>  Lors de l’appel Windows [PostThreadMessage](http://msdn.microsoft.com/library/windows/desktop/ms644946) fonction d’une application MFC, le message MFC gestionnaires ne sont pas appelés. Pour plus d’informations, consultez l’article de la Base de connaissances, « PRB : MFC Message Gestionnaire pas appelée avec PostThreadMessage() » (Q142415).  
  
##  <a name="a-namepretranslatemessagea--cwinthreadpretranslatemessage"></a><a name="pretranslatemessage"></a>CWinThread::PreTranslateMessage  
 Remplacez cette fonction pour filtrer les messages de fenêtre avant leur distribution aux fonctions Windows [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) et [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934).  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Paramètres  
 `pMsg`  
 Pointe vers une [structure MSG](../../mfc/reference/msg-structure1.md) contenant le message à traiter.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le message a été entièrement traité dans `PreTranslateMessage` et ne doit pas être traitée ultérieurement. Zéro si le message doit être traité de façon normale.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre est utilisée uniquement dans les threads d’interface utilisateur.  
  
##  <a name="a-nameprocessmessagefiltera--cwinthreadprocessmessagefilter"></a><a name="processmessagefilter"></a>CWinThread::ProcessMessageFilter  
 La fonction de raccordement de l’infrastructure appelle cette fonction membre pour filtrer et réponde à certains messages Windows.  
  
```  
virtual BOOL ProcessMessageFilter(
    int code,  
    LPMSG lpMsg);
```  
  
### <a name="parameters"></a>Paramètres  
 `code`  
 Spécifie un code de raccordement. Cette fonction membre utilise le code pour déterminer comment traiter`lpMsg.`  
  
 `lpMsg`  
 Un pointeur vers un Windows [structure MSG](../../mfc/reference/msg-structure1.md).  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le message est traité ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Une fonction de raccordement traite les événements avant de les envoyer à un message normal de l’application de traitement.  
  
 Si vous substituez cette fonctionnalité avancée, veillez à appeler la version classe de base pour maintenir l’infrastructure de raccordement de traitement.  
  
##  <a name="a-nameprocesswndprocexceptiona--cwinthreadprocesswndprocexception"></a><a name="processwndprocexception"></a>CWinThread::ProcessWndProcException  
 L’infrastructure appelle cette fonction membre, chaque fois que le gestionnaire n’intercepte pas une exception levée dans les messages de votre thread ou gestionnaires de commandes.  
  
```  
virtual LRESULT ProcessWndProcException(
    CException* e,  
    const MSG* pMsg);
```  
  
### <a name="parameters"></a>Paramètres  
 *e*  
 Pointe vers une exception non gérée.  
  
 `pMsg`  
 Pointe vers une [structure MSG](../../mfc/reference/msg-structure1.md) contenant des informations sur le message windows qui a provoqué le framework lève une exception.  
  
### <a name="return-value"></a>Valeur de retour  
 – 1 si une `WM_CREATE` exception est générée ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 N’appelez pas directement cette fonction membre.  
  
 L’implémentation par défaut de cette fonction membre gère uniquement les exceptions générées à partir des messages suivants :  
  
|Commande|Action|  
|-------------|------------|  
|`WM_CREATE`|En cas d’échec.|  
|`WM_PAINT`|Valider la fenêtre affectée, empêchant ainsi un autre `WM_PAINT` message d’être générée.|  
  
 Remplacez cette fonction membre pour fournir la gestion globale de vos exceptions. Appeler la fonctionnalité de base uniquement si vous souhaitez afficher le comportement par défaut.  
  
 Cette fonction membre est utilisée uniquement dans les threads qui ont une pompe de messages.  
  
##  <a name="a-namepumpmessagea--cwinthreadpumpmessage"></a><a name="pumpmessage"></a>CWinThread::PumpMessage  
 Contient la boucle de messages du thread.  
  
```  
virtual BOOL PumpMessage();
```  
  
### <a name="remarks"></a>Remarques  
 `PumpMessage`contient la boucle de messages du thread. **PumpMessage ne** est appelée par `CWinThread` pour pomper les messages du thread. Vous pouvez appeler `PumpMessage` directement pour forcer les messages à traiter, ou vous pouvez remplacer `PumpMessage` pour modifier son comportement par défaut.  
  
 L’appel `PumpMessage` directement et son comportement par défaut est recommandée aux utilisateurs expérimentés uniquement.  
  
##  <a name="a-nameresumethreada--cwinthreadresumethread"></a><a name="resumethread"></a>CWinThread::ResumeThread  
 Appelé pour reprendre l’exécution d’un thread qui a été suspendue par la [SuspendThread](#suspendthread) fonction membre ou un thread créé avec la **CREATE_SUSPENDED** indicateur.  
  
```  
DWORD ResumeThread();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le thread du précédent suspendre le nombre de cas de réussite ; `0xFFFFFFFF` dans le cas contraire. Si la valeur de retour est zéro, le thread actuel n’a pas suspendu. Si la valeur de retour est un, le thread a été suspendu, mais il est redémarré maintenant. Toute valeur de retour supérieur à un signifie que le thread reste interrompue.  
  
### <a name="remarks"></a>Notes  
 Le compteur de suspension du thread actuel est diminué d’une unité. Si le compteur de suspension est réduit à zéro, le thread reprend son exécution ; dans le cas contraire, le thread reste interrompu.  
  
##  <a name="a-nameruna--cwinthreadrun"></a><a name="run"></a>CWinThread::Run  
 Fournit une boucle de message par défaut pour les threads d’interface utilisateur.  
  
```  
virtual int Run();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un `int` valeur retournée par le thread. Cette valeur peut être récupérée en appelant [GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190).  
  
### <a name="remarks"></a>Remarques  
 **Exécutez** acquiert et distribue des messages de Windows jusqu'à ce que l’application reçoit une [WM_QUIT](http://msdn.microsoft.com/library/windows/desktop/ms632641) message. Si la file d’attente de messages du thread ne contient actuellement aucun message, **exécuter** appelle `OnIdle` pour exécuter le traitement des temps d’inactivité. Les messages entrants atteindre la [PreTranslateMessage](#pretranslatemessage) fonction membre pour un traitement spécial, puis à la fonction [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) pour la traduction de clavier standard. Enfin, le [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows fonction est appelée.  
  
 **Exécutez** est rarement substituée, mais vous pouvez la remplacer pour implémenter un comportement spécial.  
  
 Cette fonction membre est utilisée uniquement dans les threads d’interface utilisateur.  
  
##  <a name="a-namesetthreadprioritya--cwinthreadsetthreadpriority"></a><a name="setthreadpriority"></a>CWinThread::SetThreadPriority  
 Cette fonction définit le niveau de priorité du thread actuel dans sa classe de priorité.  
  
```  
BOOL SetThreadPriority(int nPriority);
```  
  
### <a name="parameters"></a>Paramètres  
 `nPriority`  
 Spécifie le nouveau niveau de priorité de thread dans sa classe de priorité. Ce paramètre doit être une des valeurs suivantes, répertoriées de la priorité la plus élevée à la plus faible :  
  
- **THREAD_PRIORITY_TIME_CRITICAL**  
  
- **THREAD_PRIORITY_HIGHEST**  
  
- **THREAD_PRIORITY_ABOVE_NORMAL**  
  
- **THREAD_PRIORITY_NORMAL**  
  
- **THREAD_PRIORITY_BELOW_NORMAL**  
  
- **NIVEAU DE PRIORITÉ**  
  
- **THREAD_PRIORITY_IDLE**  
  
 Pour plus d’informations sur ces priorités, consultez [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la fonction réussit ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Il peut uniquement être appelée après [CreateThread](#createthread) retourne avec succès.  
  
##  <a name="a-namesuspendthreada--cwinthreadsuspendthread"></a><a name="suspendthread"></a>CWinThread::SuspendThread  
 Incrémente en cours de suspension du thread count.  
  
```  
DWORD SuspendThread();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le thread du précédent suspendre le nombre de cas de réussite ; `0xFFFFFFFF` dans le cas contraire.  
  
### <a name="remarks"></a>Remarques  
 Si n’importe quel thread possède un compteur de suspension supérieur à zéro, ce thread ne s’exécute pas. Le thread peut être repris en appelant le [ResumeThread](#resumethread) fonction membre.  
  
## <a name="see-also"></a>Voir aussi  
 [CCmdTarget (classe)](../../mfc/reference/ccmdtarget-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CWinApp (classe)](../../mfc/reference/cwinapp-class.md)   
 [CCmdTarget (classe)](../../mfc/reference/ccmdtarget-class.md)

