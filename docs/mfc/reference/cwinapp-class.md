---
title: CWinApp (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinApp
- hInstance
dev_langs:
- C++
helpviewer_keywords:
- CWinApp class
- application objects [C++]
- HINSTANCE
- main object
ms.assetid: e426a3cd-0d15-40d6-bd55-beaa5feb2343
caps.latest.revision: 27
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
ms.openlocfilehash: 292816c8f753a7b47b563a3fcd0fa336e08acd6a
ms.lasthandoff: 02/24/2017

---
# <a name="cwinapp-class"></a>CWinApp (classe)
Classe de base à partir de laquelle vous dérivez un objet application Windows.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CWinApp : public CWinThread  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CWinApp::CWinApp](#cwinapp)|Construit un objet `CWinApp`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CWinApp::AddDocTemplate](#adddoctemplate)|Ajoute un modèle de document à la liste l’application de modèles de document disponibles.|  
|[CWinApp::AddToRecentFileList](#addtorecentfilelist)|Ajoute un nom de fichier à la liste des fichiers récemment utilisée (MRU).|  
|[CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)|Appelé par l’infrastructure lorsque l’application se ferme de façon inattendue.|  
|[CWinApp::CloseAllDocuments](#closealldocuments)|Ferme tous les documents ouverts.|  
|[CWinApp::CreatePrinterDC](#createprinterdc)|Crée un contexte de périphérique.|  
|[CWinApp::DelRegTree](#delregtree)|Supprime une clé spécifiée et toutes ses sous-clés.|  
|[CWinApp::DoMessageBox](#domessagebox)|Implémente [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox) pour l’application.|  
|[CWinApp::DoWaitCursor](#dowaitcursor)|Active le curseur d’attente et désactive.|  
|[CWinApp::EnableD2DSupport](#enabled2dsupport)|Permet à application `D2D` prennent en charge. Appelez cette méthode avant que la fenêtre principale soit initialisée.|  
|[CWinApp::EnableHtmlHelp](#enablehtmlhelp)|Implémente HTMLHelp pour l’application, au lieu de WinHelp.|  
|[CWinApp::EnableTaskbarInteraction](#enabletaskbarinteraction)|Permet l’interaction de la barre des tâches.|  
|[CWinApp::ExitInstance](#exitinstance)|Substituez pour nettoyer lorsque votre application s’arrête.|  
|[CWinApp::GetApplicationRecoveryParameter](#getapplicationrecoveryparameter)|Récupère le paramètre d’entrée pour la méthode de récupération d’application.|  
|[CWinApp::GetApplicationRecoveryPingInterval](#getapplicationrecoverypinginterval)|Retourne la longueur de temps pendant lequel le Gestionnaire de redémarrage attend que la fonction de rappel de récupération à retourner.|  
|[CWinApp::GetApplicationRestartFlags](#getapplicationrestartflags)|Renvoie les indicateurs du Gestionnaire de redémarrage.|  
|[CWinApp::GetAppRegistryKey](#getappregistrykey)|Retourne la clé de HKEY_CURRENT_USER\\« Logiciel » \RegistryKey\ProfileName.|  
|[CWinApp::GetDataRecoveryHandler](#getdatarecoveryhandler)|Obtient le Gestionnaire de récupération de données pour cette instance de l’application.|  
|[CWinApp::GetFirstDocTemplatePosition](#getfirstdoctemplateposition)|Récupère la position du premier modèle de document.|  
|[CWinApp::GetHelpMode](#gethelpmode)|Récupère le type d’aide utilisée par l’application.|  
|[CWinApp::GetNextDocTemplate](#getnextdoctemplate)|Récupère la position d’un modèle de document. Peut être utilisé de manière récursive.|  
|[CWinApp::GetPrinterDeviceDefaults](#getprinterdevicedefaults)|Récupère l’imprimante par défaut du périphérique.|  
|[CWinApp::GetProfileBinary](#getprofilebinary)|Récupère les données binaires à partir d’une entrée dans l’application. Fichier INI.|  
|[CWinApp::GetProfileInt](#getprofileint)|Récupère un entier d’une entrée dans l’application. Fichier INI.|  
|[CWinApp::GetProfileString](#getprofilestring)|Récupère une chaîne à partir d’une entrée dans l’application. Fichier INI.|  
|[CWinApp::GetSectionKey](#getsectionkey)|Retourne la clé de HKEY_CURRENT_USER\\« Logiciel » \RegistryKey\AppName\lpszSection.|  
|[CWinApp::HideApplication](#hideapplication)|Masque l’application avant de fermer tous les documents.|  
|[CWinApp::HtmlHelp](#htmlhelp)|Appelle le `HTMLHelp` fonction Windows.|  
|[CWinApp::InitInstance](#initinstance)|Substituez pour effectuer une initialisation instance Windows, telles que la création de vos objets de fenêtre.|  
|[CWinApp::IsTaskbarInteractionEnabled](#istaskbarinteractionenabled)|Indique si l’interaction de la barre des tâches de Windows 7 est activée.|  
|[CWinApp::LoadCursor](#loadcursor)|Charge une ressource de type curseur.|  
|[CWinApp::LoadIcon](#loadicon)|Charge une ressource d’icône.|  
|[CWinApp::LoadOEMCursor](#loadoemcursor)|Charge un OEM Windows prédéfinis de curseur qui le **OCR_** constantes spécifient dans WINDOWS. H.|  
|[CWinApp::LoadOEMIcon](#loadoemicon)|Charge une icône prédéfinie Windows OEM qui le **OIC_** constantes spécifient dans WINDOWS. H.|  
|[CWinApp::LoadStandardCursor](#loadstandardcursor)|Charge un Windows prédéfinis de curseur qui le **IDC_** constantes spécifient dans WINDOWS. H.|  
|[CWinApp::LoadStandardIcon](#loadstandardicon)|Charge une icône prédéfinie de Windows qui les **IDI_** constantes spécifient dans WINDOWS. H.|  
|[CWinApp::OnDDECommand](#onddecommand)|Appelée par l’infrastructure en réponse à un dynamic data exchange (DDE) exécuter la commande.|  
|[CWinApp::OnIdle](#onidle)|Substituez pour effectuer le traitement des temps d’inactivité spécifique à l’application.|  
|[CWinApp::OpenDocumentFile](#opendocumentfile)|Appelé par l’infrastructure pour ouvrir un document à partir d’un fichier.|  
|[CWinApp::ParseCommandLine](#parsecommandline)|Analyse des paramètres et des indicateurs dans la ligne de commande.|  
|[CWinApp::PreTranslateMessage](#pretranslatemessage)|Filtre les messages avant leur distribution aux fonctions Windows [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) et [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934).|  
|[CWinApp::ProcessMessageFilter](#processmessagefilter)|Intercepte certains messages avant qu’ils atteignent l’application.|  
|[CWinApp::ProcessShellCommand](#processshellcommand)|Gère les indicateurs et les arguments de ligne de commande.|  
|[CWinApp::ProcessWndProcException](#processwndprocexception)|Intercepte toutes les exceptions non gérées levées par les gestionnaires de commandes et de message de l’application.|  
|[CWinApp::Register](#register)|Effectue l’enregistrement personnalisé.|  
|[CWinApp::RegisterWithRestartManager](#registerwithrestartmanager)|Enregistre l’application avec le Gestionnaire de redémarrage.|  
|[CWinApp::ReopenPreviousFilesAtRestart](#reopenpreviousfilesatrestart)|Détermine si le Gestionnaire de redémarrage s’ouvre à nouveau les fichiers ont lors de l’application s’est terminé de façon inattendue.|  
|[CWinApp::RestartInstance](#restartinstance)|Gère le redémarrage d’une application lancé par le Gestionnaire de redémarrage.|  
|[CWinApp::RestoreAutosavedFilesAtRestart](#restoreautosavedfilesatrestart)|Détermine si le Gestionnaire de redémarrage restaure les fichiers enregistrée automatiquement lorsqu’elle redémarre l’application.|  
|[CWinApp::Run](#run)|Exécute la boucle de message par défaut. Remplacement pour personnaliser la boucle de message.|  
|[CWinApp::RunAutomated](#runautomated)|Tests de ligne de commande de l’application pour le **/Automation** option. Obsolète. Au lieu de cela, utilisez la valeur de [CCommandLineInfo::m_bRunAutomated](../../mfc/reference/ccommandlineinfo-class.md#m_brunautomated) après avoir appelé [ParseCommandLine](#parsecommandline).|  
|[CWinApp::RunEmbedded](#runembedded)|Tests de ligne de commande de l’application pour le **/Embedding** option. Obsolète. Au lieu de cela, utilisez la valeur de [CCommandLineInfo::m_bRunEmbedded](../../mfc/reference/ccommandlineinfo-class.md#m_brunembedded) après avoir appelé [ParseCommandLine](#parsecommandline).|  
|[CWinApp::SaveAllModified](#saveallmodified)|Invite l’utilisateur à enregistrer les documents modifiés tous.|  
|[CWinApp::SelectPrinter](#selectprinter)|Sélectionne une imprimante précédemment indiquée par un utilisateur via une boîte de dialogue d’impression.|  
|[CWinApp::SetHelpMode](#sethelpmode)|Définit et initialise le type d’aide utilisée par l’application.|  
|[CWinApp::SupportsApplicationRecovery](#supportsapplicationrecovery)|Détermine si le Gestionnaire de redémarrage permet de récupérer une application qui s’est terminé de façon inattendue.|  
|[CWinApp::SupportsAutosaveAtInterval](#supportsautosaveatinterval)|Détermine si le Gestionnaire de redémarrage enregistre automatiquement ouvre des documents à intervalles réguliers.|  
|[CWinApp::SupportsAutosaveAtRestart](#supportsautosaveatrestart)|Détermine si le Gestionnaire de redémarrage enregistre automatiquement les documents ouverts lorsque l’application redémarre.|  
|[CWinApp::SupportsRestartManager](#supportsrestartmanager)|Détermine si l’application prend en charge le Gestionnaire de redémarrage.|  
|[CWinApp::Unregister](#unregister)|Annule l’inscription de tous les éléments connus pour être enregistrés par le `CWinApp` objet.|  
|[CWinApp::WinHelp](#winhelp)|Appelle le `WinHelp` fonction Windows.|  
|[CWinApp::WriteProfileBinary](#writeprofilebinary)|Écrit des données binaires à une entrée de l’application. Fichier INI.|  
|[CWinApp::WriteProfileInt](#writeprofileint)|Écrit un entier à une entrée de l’application. Fichier INI.|  
|[CWinApp::WriteProfileString](#writeprofilestring)|Écrit une chaîne à une entrée de l’application. Fichier INI.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CWinApp::EnableShellOpen](#enableshellopen)|Permet à l’utilisateur d’ouvrir des fichiers de données à partir du Gestionnaire de fichiers Windows.|  
|[CWinApp::LoadStdProfileSettings](#loadstdprofilesettings)|Norme de charges. Paramètres du fichier INI et Active les derniers fichiers fonctionnalité liste.|  
|[CWinApp::OnContextHelp](#oncontexthelp)|Gère MAJ + F1 dans l’application.|  
|[CWinApp::OnFileNew](#onfilenew)|Implémente la `ID_FILE_NEW` commande.|  
|[CWinApp::OnFileOpen](#onfileopen)|Implémente la `ID_FILE_OPEN` commande.|  
|[CWinApp::OnFilePrintSetup](#onfileprintsetup)|Implémente la `ID_FILE_PRINT_SETUP` commande.|  
|[CWinApp::OnHelp](#onhelp)|Gère l'aide F1 dans l'application (en utilisant le contexte actuel).|  
|[CWinApp::OnHelpFinder](#onhelpfinder)|Gère les commandes `ID_HELP_FINDER` et `ID_DEFAULT_HELP`.|  
|[CWinApp::OnHelpIndex](#onhelpindex)|Gère la commande `ID_HELP_INDEX` et fournit une rubrique d'aide par défaut.|  
|[CWinApp::OnHelpUsing](#onhelpusing)|Gère la commande `ID_HELP_USING`.|  
|[CWinApp::RegisterShellFileTypes](#registershellfiletypes)|Inscrit les types de documents de toute l’application avec le Gestionnaire de fichiers Windows.|  
|[CWinApp::SetAppID](#setappid)|ID de modèle d’Application utilisateur définit de manière explicite pour l’application. Cette méthode doit être appelée avant que l’interface utilisateur est présentée à l’utilisateur (le meilleur emplacement est le constructeur d’application).|  
|[CWinApp::SetRegistryKey](#setregistrykey)|Provoque des paramètres d’application sont stockées dans le Registre au lieu de. Fichiers INI.|  
|[CWinApp::UnregisterShellFileTypes](#unregistershellfiletypes)|Annule l’inscription des types de documents de toute l’application avec le Gestionnaire de fichiers Windows.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CWinApp::m_bHelpMode](#m_bhelpmode)|Indique si l’utilisateur est en mode de contexte d’aide (généralement appelé avec MAJ + F1).|  
|[CWinApp::m_eHelpType](#m_ehelptype)|Spécifie le type d’aide utilisée par l’application.|  
|[CWinApp::m_hInstance](#m_hinstance)|Identifie l’instance actuelle de l’application.|  
|[CWinApp::m_lpCmdLine](#m_lpcmdline)|Pointe vers une chaîne terminée par le caractère null qui spécifie la ligne de commande pour l’application.|  
|[CWinApp::m_nCmdShow](#m_ncmdshow)|Spécifie comment la fenêtre doit être affichée.|  
|[CWinApp::m_pActiveWnd](#m_pactivewnd)|Pointeur vers la fenêtre principale de l’application de conteneur lorsqu’un serveur OLE est actif sur place.|  
|[CWinApp::m_pszAppID](#m_pszappid)|ID du modèle application utilisateur.|  
|[CWinApp::m_pszAppName](#m_pszappname)|Spécifie le nom de l’application.|  
|[CWinApp::m_pszExeName](#m_pszexename)|Le nom du module de l’application.|  
|[CWinApp::m_pszHelpFilePath](#m_pszhelpfilepath)|Le chemin d’accès au fichier d’aide de l’application.|  
|[CWinApp::m_pszProfileName](#m_pszprofilename)|L’application. Nom du fichier INI.|  
|[CWinApp::m_pszRegistryKey](#m_pszregistrykey)|Utilisé pour déterminer la clé de Registre complet pour le stockage des paramètres de profil d’application.|  
  
### <a name="protected-data-members"></a>Membres de données protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CWinApp::m_dwRestartManagerSupportFlags](#m_dwrestartmanagersupportflags)|Indicateurs qui déterminent le comportement du Gestionnaire de redémarrage.|  
|[CWinApp::m_nAutosaveInterval](#m_nautosaveinterval)|La durée en millisecondes entre enregistre automatiquement.|  
|[CWinApp::m_pDataRecoveryHandler](#m_pdatarecoveryhandler)|Pointeur vers le Gestionnaire de récupération de données pour l’application.|  
  
## <a name="remarks"></a>Notes  
 Un objet d’application fournit des fonctions membres pour initialiser votre application (et chaque instance) et pour l’exécution de l’application.  
  
 Chaque application qui utilise les classes Microsoft Foundation ne peut contenir un objet dérivé de `CWinApp`. Cet objet est créée lors de l’établissement des autres objets globaux C++ et est déjà disponible lorsque Windows appelle le `WinMain` (fonction), qui est fournie par la bibliothèque Microsoft Foundation Class. Déclarez votre dérivée `CWinApp` objet au niveau global.  
  
 Lorsque vous dérivez une classe d’application à partir de `CWinApp`, remplacer le [InitInstance](#initinstance) fonction membre pour créer l’objet de fenêtre principale de votre application.  
  
 Outre la `CWinApp` , fonctions membres de la bibliothèque Microsoft Foundation Class fournit les fonctions globales suivantes pour accéder à votre `CWinApp` objet et autres informations globales :  
  
- [AfxGetApp](application-information-and-management.md#afxgetapp) Obtient un pointeur vers le `CWinApp` objet.  
  
- [AfxGetInstanceHandle](application-information-and-management.md#afxgetinstancehandle) Obtient un handle vers l’instance d’application actuelle.  
  
- [AfxGetResourceHandle](application-information-and-management.md#afxgetresourcehandle) Obtient un handle vers des ressources de l’application.  
  
- [AfxGetAppName](application-information-and-management.md#afxgetappname) Obtient un pointeur vers une chaîne contenant le nom de l’application. Ou bien, si vous avez un pointeur vers le `CWinApp` de l’objet, utilisez `m_pszExeName` pour obtenir le nom de l’application.  
  
 Consultez la page [CWinApp : la classe d’Application](../../mfc/cwinapp-the-application-class.md) pour plus d’informations sur la `CWinApp` classe, y compris une vue d’ensemble des opérations suivantes :  
  
- `CWinApp`-dérivées du code écrit par l’Assistant Application.  
  
- `CWinApp`du rôle dans l’ordre d’exécution de votre application.  
  
- `CWinApp`'s les implémentations de fonction membre par défaut.  
  
- `CWinApp`de clé remplaçable.  
  
 Le **m_hPrevInstance** membre de données n’existe plus. Pour plus d’informations sur la détection d’une instance précédente de `CWinApp`, consultez l’article de la Base de connaissances « Comment identifier un précédent Instance d’une Application » (KB106385) à l’adresse [http://support.microsoft.com/default.aspxscid=kb;en-us;106385](http://support.microsoft.com/default.aspxscid=kb;en-us;106385).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 `CWinApp`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h  
  
##  <a name="a-nameadddoctemplatea--cwinappadddoctemplate"></a><a name="adddoctemplate"></a>CWinApp::AddDocTemplate  
 Appelez cette fonction membre pour ajouter un modèle de document à la liste des modèles de document disponibles qui tient à jour l’application.  
  
```  
void AddDocTemplate(CDocTemplate* pTemplate);
```  
  
### <a name="parameters"></a>Paramètres  
 `pTemplate`  
 Un pointeur vers le `CDocTemplate` à ajouter.  
  
### <a name="remarks"></a>Remarques  
 Vous devez ajouter tous les modèles à une application de document avant d’appeler [RegisterShellFileTypes](#registershellfiletypes).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#35;](../../mfc/reference/codesnippet/cpp/cwinapp-class_1.cpp)]  
  
##  <a name="a-nameaddtorecentfilelista--cwinappaddtorecentfilelist"></a><a name="addtorecentfilelist"></a>CWinApp::AddToRecentFileList  
 Appelez cette fonction membre pour ajouter `lpszPathName` à la liste des derniers fichiers utilisés.  
  
```  
virtual void AddToRecentFileList(LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszPathName`  
 Chemin d’accès au fichier.  
  
### <a name="remarks"></a>Remarques  
 Vous devez appeler le [LoadStdProfileSettings](#loadstdprofilesettings) fonction membre pour charger la liste des fichiers MRU actuelle avant d’utiliser cette fonction membre.  
  
 L’infrastructure appelle cette fonction membre lorsqu’il ouvre un fichier ou exécute la commande Enregistrer sous pour enregistrer un fichier avec un nouveau nom.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing n °&36;](../../mfc/reference/codesnippet/cpp/cwinapp-class_2.cpp)]  
  
##  <a name="a-nameapplicationrecoverycallbacka--cwinappapplicationrecoverycallback"></a><a name="applicationrecoverycallback"></a>CWinApp::ApplicationRecoveryCallback  
 Appelé par l’infrastructure lorsque l’application se ferme de façon inattendue.  
  
```  
virtual DWORD ApplicationRecoveryCallback(LPVOID lpvParam);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpvParam`  
 Réservé à un usage ultérieur.  
  
### <a name="return-value"></a>Valeur de retour  
 0 si cette méthode a réussi ; différent de zéro si une erreur se produit.  
  
### <a name="remarks"></a>Notes  
 Si votre application prend en charge le Gestionnaire de redémarrage, l’infrastructure appelle cette fonction lorsque votre application se ferme de façon inattendue.  
  
 L’implémentation par défaut de `ApplicationRecoveryCallback` utilise le `CDataRecoveryHandler` pour enregistrer la liste des documents actuellement ouverts dans le Registre. Cette méthode n’effectue pas automatiquement tous les fichiers.  
  
 Pour personnaliser le comportement, remplacez cette fonction dans un dérivé [CWinApp (classe)](../../mfc/reference/cwinapp-class.md) ou passer votre propre méthode de récupération d’application en tant que paramètre [CWinApp::RegisterWithRestartManager](#registerwithrestartmanager).  
  
##  <a name="a-nameclosealldocumentsa--cwinappclosealldocuments"></a><a name="closealldocuments"></a>CWinApp::CloseAllDocuments  
 Appelez cette fonction membre pour fermer tous les documents ouverts avant de quitter.  
  
```  
void CloseAllDocuments(BOOL bEndSession);
```  
  
### <a name="parameters"></a>Paramètres  
 `bEndSession`  
 Spécifie si la session Windows en cours terminée. Il est **TRUE** si la session est terminée ; sinon **FALSE**.  
  
### <a name="remarks"></a>Notes  
 Appelez [HideApplication](#hideapplication) avant d’appeler `CloseAllDocuments`.  
  
##  <a name="a-namecreateprinterdca--cwinappcreateprinterdc"></a><a name="createprinterdc"></a>CWinApp::CreatePrinterDC  
 Appelez cette fonction membre pour créer un contexte de périphérique (DC) imprimante à partir de l’imprimante sélectionnée.  
  
```  
BOOL CreatePrinterDC(CDC& dc);
```  
  
### <a name="parameters"></a>Paramètres  
 `dc`  
 Une référence à un contexte de périphérique.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le contexte de l’imprimante est créé avec succès ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 `CreatePrinterDC`Initialise le contexte de périphérique que vous passez par référence, donc vous pouvez l’utiliser pour imprimer.  
  
 Si la fonction réussite, lorsque vous avez terminé l’impression, vous devez détruire le contexte de périphérique. Vous pouvez laisser le destructeur de la [CDC](../../mfc/reference/cdc-class.md) objet faire ou vous pouvez le faire explicitement en appelant [CDC::DeleteDC](../../mfc/reference/cdc-class.md#deletedc).  
  
##  <a name="a-namecwinappa--cwinappcwinapp"></a><a name="cwinapp"></a>CWinApp::CWinApp  
 Construit un `CWinApp` objet et lui transmet `lpszAppName` comme nom de l’application.  
  
```  
CWinApp(LPCTSTR lpszAppName = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszAppName`  
 Chaîne terminée par le caractère null qui contient le nom de l’application qui utilise Windows. Si cet argument n’est fourni ou est **NULL**, `CWinApp` utilise la chaîne de ressource **AFX_IDS_APP_TITLE** ou le nom de fichier du fichier exécutable.  
  
### <a name="remarks"></a>Remarques  
 Vous devez construire un objet global de votre `CWinApp`-classe dérivée. Vous pouvez avoir un seul `CWinApp` objet dans votre application. Le constructeur stocke un pointeur vers le `CWinApp` objet afin que `WinMain` peuvent appeler des fonctions pour initialiser et exécuter l’application de membres de l’objet.  
  
##  <a name="a-namedelregtreea--cwinappdelregtree"></a><a name="delregtree"></a>CWinApp::DelRegTree  
 Supprime une clé de Registre spécifiques et toutes ses sous-clés.  
  
```  
LONG DelRegTree(
    HKEY hParentKey,  
    const CString& strKeyName);

 
LONG DelRegTree(
    HKEY hParentKey,
    const CString& strKeyName,
    CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 *hParentKey*  
 Handle vers une clé de Registre.  
  
 *strKeyName*  
 Le nom de la clé de Registre à supprimer.  
  
 *pTM*  
 Pointeur vers l’objet CAtlTransactionManager.  
  
### <a name="return-value"></a>Valeur de retour  
 Si la fonction réussit, la valeur de retour est ERROR_SUCCESS. Si la fonction échoue, la valeur de retour est un code d’erreur différent de zéro défini dans Winerror.h.  
  
### <a name="remarks"></a>Notes  
 Appelez cette fonction pour supprimer la clé et ses sous-clés.  
  
##  <a name="a-namedomessageboxa--cwinappdomessagebox"></a><a name="domessagebox"></a>CWinApp::DoMessageBox  
 L’infrastructure appelle cette fonction membre pour implémenter une boîte de message pour la fonction globale [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox).  
  
```  
virtual int DoMessageBox(
    LPCTSTR lpszPrompt,  
    UINT nType,  
    UINT nIDPrompt);
```  
  
### <a name="parameters"></a>Paramètres  
 *lpszPrompt*  
 Adresse du texte dans la boîte de message.  
  
 `nType`  
 La boîte de message [style](../../mfc/reference/message-box-styles.md).  
  
 `nIDPrompt`  
 L’index d’une chaîne de contexte d’aide.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne les mêmes valeurs que `AfxMessageBox`.  
  
### <a name="remarks"></a>Remarques  
 N’appelez pas cette fonction membre pour ouvrir une boîte de message. Utilisez `AfxMessageBox` à la place.  
  
 Remplacez cette fonction membre pour personnaliser le traitement de l’application de `AfxMessageBox` appelle.  
  
##  <a name="a-namedowaitcursora--cwinappdowaitcursor"></a><a name="dowaitcursor"></a>CWinApp::DoWaitCursor  
 Cette fonction membre est appelée par l’infrastructure pour implémenter [CWaitCursor](../../mfc/reference/cwaitcursor-class.md), [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor), [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor), et [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor).  
  
```  
virtual void DoWaitCursor(int nCode);
```  
  
### <a name="parameters"></a>Paramètres  
 `nCode`  
 Si ce paramètre est 1, un curseur d’attente s’affiche. Si 0, le curseur d’attente est restauré sans incrémenter le décompte de références. Si la valeur –&1;, le curseur d’attente se termine.  
  
### <a name="remarks"></a>Remarques  
 La valeur par défaut implémente un sablier. `DoWaitCursor`conserve un décompte de références. Lorsqu’il est positif, le curseur sablier s’affiche.  
  
 Bien que vous n’appelez pas normalement `DoWaitCursor` directement, vous pouvez substituer cette fonction membre pour modifier le curseur d’attente ou pour effectuer un traitement supplémentaire lorsque le curseur d’attente s’affiche.  
  
 Pour un moyen plus facile, plus simple d’implémenter un curseur d’attente, utilisez `CWaitCursor`.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#37;](../../mfc/reference/codesnippet/cpp/cwinapp-class_3.cpp)]  
  
##  <a name="a-nameenabled2dsupporta--cwinappenabled2dsupport"></a><a name="enabled2dsupport"></a>CWinApp::EnableD2DSupport  
 [!INCLUDE[dev10_sp1required](../../mfc/reference/includes/dev10_sp1required_md.md)]  
  
 Permet la prise en charge des applications D2D. Appelez cette méthode avant que la fenêtre principale soit initialisée.  
  
```  
BOOL EnableD2DSupport(
D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,  
DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```  
  
### <a name="parameters"></a>Paramètres  
 `d2dFactoryType`  
 Le modèle de thread de la fabrique D2D et des ressources qu’il crée.  
  
 `writeFactoryType`  
 Une valeur qui indique si l’objet de fabrique d’écriture sera être partagé ou isolé  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur TRUE si prise en charge D2D a été activé :  
  
##  <a name="a-nameenablehtmlhelpa--cwinappenablehtmlhelp"></a><a name="enablehtmlhelp"></a>CWinApp::EnableHtmlHelp  
 Appelez cette fonction membre à partir de dans le constructeur de votre `CWinApp`-dérivée de la classe pour utiliser HTMLHelp pour l’aide de votre application.  
  
```  
void EnableHtmlHelp();
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameenableshellopena--cwinappenableshellopen"></a><a name="enableshellopen"></a>CWinApp::EnableShellOpen  
 Appelez cette fonction, généralement à partir de votre `InitInstance` remplacement, pour permettre aux utilisateurs de votre application ouvrir les fichiers de données lorsqu’ils double-cliquer sur les fichiers de dans le Gestionnaire de fichiers Windows.  
  
```  
void EnableShellOpen();
```  
  
### <a name="remarks"></a>Notes  
 Appelez le `RegisterShellFileTypes` fonctionne conjointement avec cette fonction membre, ou fournir un. Fichier REG avec votre application pour l’inscription manuelle des types de documents.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#38;](../../mfc/reference/codesnippet/cpp/cwinapp-class_4.cpp)]  
  
##  <a name="a-nameenabletaskbarinteractiona--cwinappenabletaskbarinteraction"></a><a name="enabletaskbarinteraction"></a>CWinApp::EnableTaskbarInteraction  
 Permet l’interaction de la barre des tâches.  
  
```  
BOOL EnableTaskbarInteraction(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `bEnable`  
 Spécifie si l’interaction avec la barre des tâches Windows 7 doit être activée ( `TRUE`), ou désactivé ( `FALSE`).  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `TRUE` si l’interaction de la barre des tâches peut être activée ou désactivée.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode doit être appelée avant la création de la fenêtre principale, sinon elle déclare et renvoie `FALSE`.  
  
##  <a name="a-nameexitinstancea--cwinappexitinstance"></a><a name="exitinstance"></a>CWinApp::ExitInstance  
 Appelée par l’infrastructure dans le **exécuter** fonction membre pour quitter cette instance de l’application.  
  
```  
virtual int ExitInstance();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Code de sortie de l’application ; 0 n’indique aucune erreur, et les valeurs supérieures à 0 indiquent une erreur. Cette valeur est utilisée comme valeur de retour de `WinMain`.  
  
### <a name="remarks"></a>Remarques  
 N’appelez pas cette fonction membre à partir de n’importe quel emplacement, mais dans le **exécuter** fonction membre.  
  
 L’implémentation par défaut de cette fonction écrit des options de l’infrastructure dans l’application. Fichier INI. Remplacez cette fonction pour nettoyer lorsque votre application s’arrête.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing n °&39;](../../mfc/reference/codesnippet/cpp/cwinapp-class_5.cpp)]  
  
##  <a name="a-namegetapplicationrecoveryparametera--cwinappgetapplicationrecoveryparameter"></a><a name="getapplicationrecoveryparameter"></a>CWinApp::GetApplicationRecoveryParameter  
 Récupère le paramètre d’entrée pour la méthode de récupération d’application.  
  
```  
virtual LPVOID GetApplicationRecoveryParameter();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le paramètre d’entrée par défaut pour la méthode de récupération d’application.  
  
### <a name="remarks"></a>Remarques  
 Le comportement par défaut de cette fonction renvoie `NULL`.  
  
 Pour plus d’informations, consultez [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).  
  
##  <a name="a-namegetapplicationrecoverypingintervala--cwinappgetapplicationrecoverypinginterval"></a><a name="getapplicationrecoverypinginterval"></a>CWinApp::GetApplicationRecoveryPingInterval  
 Retourne la longueur de temps pendant lequel le Gestionnaire de redémarrage attend que la fonction de rappel de récupération à retourner.  
  
```  
virtual DWORD GetApplicationRecoveryPingInterval();
```  
  
### <a name="return-value"></a>Valeur de retour  
 La durée en millisecondes.  
  
### <a name="remarks"></a>Remarques  
 Lorsqu’une application qui est enregistrée avec le Gestionnaire de redémarrage se termine de façon inattendue, l’application tente d’enregistrer les documents ouverts et appelle la fonction de rappel de récupération. La fonction de rappel de récupération par défaut est [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).  
  
 La longueur de la durée d’attente de l’infrastructure pour la fonction de rappel de récupération renvoyer est l’intervalle des requêtes ping. Vous pouvez personnaliser l’intervalle des requêtes ping en substituant `CWinApp::GetApplicationRecoveryPingInterval` ou en fournissant une valeur personnalisée à `RegisterWithRestartManager`.  
  
##  <a name="a-namegetapplicationrestartflagsa--cwinappgetapplicationrestartflags"></a><a name="getapplicationrestartflags"></a>CWinApp::GetApplicationRestartFlags  
 Renvoie les indicateurs du Gestionnaire de redémarrage.  
  
```  
virtual DWORD GetApplicationRestartFlags();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Indicateurs pour le Gestionnaire de redémarrage. L’implémentation par défaut retourne 0.  
  
### <a name="remarks"></a>Remarques  
 Les indicateurs du Gestionnaire de redémarrage n’ont aucun effet avec l’implémentation par défaut. Ils sont fournis pour une utilisation ultérieure.  
  
 Vous définissez les indicateurs lorsque vous inscrivez l’application avec le Gestionnaire de redémarrage à l’aide de [CWinApp::RegisterWithRestartManager](#registerwithrestartmanager).  
  
 Les valeurs possibles pour les indicateurs de gestionnaire de redémarrage sont comme suit :  
  
- `RESTART_NO_CRASH`  
  
- `RESTART_NO_HANG`  
  
- `RESTART_NO_PATCH`  
  
- `RESTART_NO_REBOOT`  
  
##  <a name="a-namegetappregistrykeya--cwinappgetappregistrykey"></a><a name="getappregistrykey"></a>CWinApp::GetAppRegistryKey  
 Retourne la clé de HKEY_CURRENT_USER\\« Logiciel » \RegistryKey\ProfileName.  
  
```  
HKEY GetAppRegistryKey(CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `pTM`  
 Pointeur vers un `CAtlTransactionManager` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Clé d’application si la fonction réussit ; dans le cas contraire `NULL`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetdatarecoveryhandlera--cwinappgetdatarecoveryhandler"></a><a name="getdatarecoveryhandler"></a>CWinApp::GetDataRecoveryHandler  
 Obtient le Gestionnaire de récupération de données pour cette instance de l’application.  
  
```  
virtual CDataRecoveryHandler *GetDataRecoveryHandler();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le Gestionnaire de récupération de données pour cette instance de l’application.  
  
### <a name="remarks"></a>Remarques  
 Chaque application qui utilise le Gestionnaire de redémarrage doit avoir une instance de la [CDataRecoveryHandler classe](../../mfc/reference/cdatarecoveryhandler-class.md). Cette classe est responsable du suivi des documents ouverts et des fichiers d’enregistrement automatique. Le comportement de la `CDataRecoveryHandler` dépend de la configuration du Gestionnaire de redémarrage. Pour plus d’informations, consultez [CDataRecoveryHandler classe](../../mfc/reference/cdatarecoveryhandler-class.md).  
  
 Cette méthode retourne `NULL` sur les systèmes d’exploitation antérieurs à [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]. Le Gestionnaire de redémarrage n’est pas pris en charge sur les systèmes d’exploitation antérieurs à [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)].  
  
 Si l’application ne dispose pas actuellement d’un gestionnaire de récupération de données, cette méthode crée un et retourne un pointeur vers elle.  
  
##  <a name="a-namegetfirstdoctemplatepositiona--cwinappgetfirstdoctemplateposition"></a><a name="getfirstdoctemplateposition"></a>CWinApp::GetFirstDocTemplatePosition  
 Obtient la position du premier modèle de document dans l’application.  
  
```  
POSITION GetFirstDocTemplatePosition() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 A **POSITION** valeur qui peut être utilisé pour l’itération ou l’extraction de pointeur d’objet ; **NULL** si la liste est vide.  
  
### <a name="remarks"></a>Remarques  
 Utilisez le **POSITION** valeur retournée dans un appel à [GetNextDocTemplate](#getnextdoctemplate) pour obtenir le premier [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) objet.  
  
##  <a name="a-namegethelpmodea--cwinappgethelpmode"></a><a name="gethelpmode"></a>CWinApp::GetHelpMode  
 Récupère le type d’aide utilisée par l’application.  
  
```  
AFX_HELP_TYPE GetHelpMode();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le type d’aide utilisée par l’application. Consultez la page [CWinApp::m_eHelpType](#m_ehelptype) pour plus d’informations.  
  
##  <a name="a-namegetnextdoctemplatea--cwinappgetnextdoctemplate"></a><a name="getnextdoctemplate"></a>CWinApp::GetNextDocTemplate  
 Obtient le modèle de document identifié par `pos`, puis définit `pos` à la **POSITION** valeur.  
  
```  
CDocTemplate* GetNextDocTemplate(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `pos`  
 Une référence à un **POSITION** valeur retournée par un appel précédent à `GetNextDocTemplate` ou [fonctions membres GetFirstDocTemplatePosition](#getfirstdoctemplateposition). La valeur est mise à jour vers la position suivante par cet appel.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) objet.  
  
### <a name="remarks"></a>Notes  
 Vous pouvez utiliser `GetNextDocTemplate` dans une boucle d’itération en avant si vous établissez la position initiale avec un appel à `GetFirstDocTemplatePosition`.  
  
 Vous devez vous assurer que votre **POSITION** valeur n’est valide. Si elle n’est pas valide, la version Debug de la bibliothèque Microsoft Foundation Class déclare.  
  
 Si le modèle de document récupéré est la dernière disponible, alors la nouvelle valeur de `pos` a **NULL**.  
  
##  <a name="a-namegetprinterdevicedefaultsa--cwinappgetprinterdevicedefaults"></a><a name="getprinterdevicedefaults"></a>CWinApp::GetPrinterDeviceDefaults  
 Appelez cette fonction membre pour préparer une imprimante contexte de périphérique d’impression.  
  
```  
BOOL GetPrinterDeviceDefaults(struct tagPDA* pPrintDlg);
```  
  
### <a name="parameters"></a>Paramètres  
 *pPrintDlg*  
 Un pointeur vers un [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) structure.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Récupère les valeurs par défaut d’imprimante en cours à partir de Windows. Fichier INI en tant que nécessaire, ou utilise la dernière configuration de l’imprimante définie par l’utilisateur dans la configuration de l’impression.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing numéro&40;](../../mfc/reference/codesnippet/cpp/cwinapp-class_6.cpp)]  
  
##  <a name="a-namegetprofilebinarya--cwinappgetprofilebinary"></a><a name="getprofilebinary"></a>CWinApp::GetProfileBinary  
 Appelez cette fonction membre pour récupérer des données binaires à partir d’une entrée dans une section du Registre de l’application spécifiée ou. Fichier INI.  
  
```  
BOOL GetProfileBinary(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    LPBYTE* ppData,  
    UINT* pBytes);
```  
  
### <a name="parameters"></a>Paramètres  
 *lpszSection*  
 Pointe vers une chaîne terminée par le caractère null qui spécifie la section contenant l’entrée.  
  
 *lpszEntry*  
 Pointe vers une chaîne terminée par le caractère null qui contient l’entrée dont la valeur doit être récupéré.  
  
 *ppData*  
 Pointe vers un pointeur qui reçoit l’adresse des données.  
  
 *Pétaoctets*  
 Pointe vers un UINT qui reçoit la taille des données (en octets).  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre n’est pas la casse, par conséquent, les chaînes dans le *lpszSection* et *lpszEntry* paramètres peuvent différer dans les cas.  
  
> [!NOTE]
> **GetProfileBinary** alloue une mémoire tampon et retourne son adresse dans \* *ppData*. L’appelant est responsable de la libération de la mémoire tampon à l’aide de **delete []**.  
  
> [!IMPORTANT]
>  Les données retournées par cette fonction ne sont pas nécessairement NULL s’est arrêté, et l’appelant doit exécuter une validation. Pour plus d’informations, consultez [Solutions contre les dépassements de mémoire tampon](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[# NVC_MFCWindowing&41;](../../mfc/reference/codesnippet/cpp/cwinapp-class_7.cpp)]  
  
 Pour obtenir un exemple supplémentaire, consultez [CWinApp::WriteProfileBinary](#writeprofilebinary).  
  
##  <a name="a-namegetprofileinta--cwinappgetprofileint"></a><a name="getprofileint"></a>CWinApp::GetProfileInt  
 Appelez cette fonction membre pour récupérer la valeur d’un entier à partir d’une entrée dans une section du Registre de l’application spécifiée ou. Fichier INI.  
  
```  
UINT GetProfileInt(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    int nDefault);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszSection`  
 Pointe vers une chaîne terminée par le caractère null qui spécifie la section contenant l’entrée.  
  
 `lpszEntry`  
 Pointe vers une chaîne terminée par le caractère null qui contient l’entrée dont la valeur doit être récupéré.  
  
 `nDefault`  
 Spécifie la valeur par défaut pour retourner si l’infrastructure ne peut pas trouver l’entrée.  
  
### <a name="return-value"></a>Valeur de retour  
 La valeur entière de la chaîne qui suit l’entrée spécifiée, si la fonction réussit. La valeur de retour est la valeur de le `nDefault` paramètre si la fonction ne trouve pas l’entrée. La valeur de retour est 0 si la valeur qui correspond à l’entrée spécifiée n’est pas un entier.  
  
 Cette fonction membre prend en charge la notation hexadécimale pour la valeur dans le. Fichier INI. Lorsque vous récupérez un entier signé, vous devez effectuer un cast de la valeur dans un `int`.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre n’est pas la casse, par conséquent, les chaînes dans le `lpszSection` et `lpszEntry` paramètres peuvent différer dans les cas.  
  
> [!IMPORTANT]
>  Les données retournées par cette fonction ne sont pas nécessairement NULL s’est arrêté, et l’appelant doit exécuter une validation. Pour plus d’informations, consultez [Solutions contre les dépassements de mémoire tampon](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#42;](../../mfc/reference/codesnippet/cpp/cwinapp-class_8.cpp)]  
  
 Pour obtenir un exemple supplémentaire, consultez [CWinApp::WriteProfileInt](#writeprofileint).  
  
##  <a name="a-namegetprofilestringa--cwinappgetprofilestring"></a><a name="getprofilestring"></a>CWinApp::GetProfileString  
 Appelez cette fonction membre pour récupérer la chaîne associée à une entrée dans la section spécifiée dans le Registre de l’application ou. Fichier INI.  
  
```  
CString GetProfileString(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    LPCTSTR lpszDefault = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszSection`  
 Pointe vers une chaîne terminée par le caractère null qui spécifie la section contenant l’entrée.  
  
 `lpszEntry`  
 Pointe vers une chaîne terminée par le caractère null qui contient l’entrée dont la chaîne doit être récupéré. Cette valeur ne doit pas être **NULL**.  
  
 `lpszDefault`  
 Pointe vers la valeur de chaîne par défaut pour l’entrée si l’entrée est introuvable dans le fichier d’initialisation.  
  
### <a name="return-value"></a>Valeur de retour  
 La valeur de retour est la chaîne à partir de l’application. Fichier INI ou `lpszDefault` si la chaîne est introuvable. La longueur maximale de chaîne prises en charge par le framework est `_MAX_PATH`. Si `lpszDefault` est **NULL**, la valeur de retour est une chaîne vide.  
  
### <a name="remarks"></a>Notes  
  
> [!IMPORTANT]
>  Les données retournées par cette fonction ne sont pas nécessairement NULL s’est arrêté, et l’appelant doit exécuter une validation. Pour plus d’informations, consultez [Solutions contre les dépassements de mémoire tampon](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#43;](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]  
  
 Pour un autre exemple, consultez l’exemple de [CWinApp::GetProfileInt](#getprofileint).  
  
##  <a name="a-namegetsectionkeya--cwinappgetsectionkey"></a><a name="getsectionkey"></a>CWinApp::GetSectionKey  
 Retourne la clé de HKEY_CURRENT_USER\\« Logiciel » \RegistryKey\AppName\lpszSection.  
  
```  
HKEY GetSectionKey(
LPCTSTR lpszSection,  
CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszSection`  
 Le nom de la clé doit être obtenu.  
  
 `pTM`  
 Pointeur vers un `CAtlTransactionManager` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Section clé si la fonction réussit ; dans le cas contraire `NULL`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namehideapplicationa--cwinapphideapplication"></a><a name="hideapplication"></a>CWinApp::HideApplication  
 Appelez cette fonction membre pour masquer une application avant de fermer les documents ouverts.  
  
```  
void HideApplication();
```  
  
##  <a name="a-namehtmlhelpa--cwinapphtmlhelp"></a><a name="htmlhelp"></a>CWinApp::HtmlHelp  
 Appelez cette fonction membre pour appeler l’application HTMLHelp.  
  
```  
virtual void HtmlHelp(
    DWORD_PTR dwData,  
    UINT nCmd = 0x000F);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwData`  
 Spécifie les données supplémentaires. La valeur utilisée dépend de la valeur de le `nCmd` paramètre.  
  
 `nCmd`  
 Spécifie le type d’aide demandée. Pour obtenir la liste des valeurs possibles et comment elles affectent le `dwData` paramètre, consultez le `uCommand` paramètre figurant sur l’API fonction HTMLHelp dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Notes  
 Le framework appelle également cette fonction pour appeler l’application HTMLHelp.  
  
 Le framework ferme automatiquement l’application HTMLHelp lorsque votre application s’arrête.  
  
##  <a name="a-nameinitinstancea--cwinappinitinstance"></a><a name="initinstance"></a>CWinApp::InitInstance  
 Windows autorise plusieurs copies du même programme à exécuter en même temps.  
  
```  
virtual BOOL InitInstance();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’initialisation aboutit ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Initialisation de l’application est conceptuellement divisée en deux sections : l’initialisation des applications à usage unique qui est effectuée la première fois que le programme s’exécute et initialisation d’instance qui s’exécute chaque fois une copie de l’exécution du programme, y compris la première fois. Implémentation de l’infrastructure de `WinMain` appelle cette fonction.  
  
 Substituer `InitInstance` pour initialiser chaque nouvelle instance de votre application s’exécutant sous Windows. En règle générale, vous substituez `InitInstance` pour construire votre objet fenêtre principale et définir le `CWinThread::m_pMainWnd` membre de données pour pointer vers cette fenêtre. Pour plus d’informations sur la substitution de cette fonction membre, consultez la page [CWinApp : la classe d’Application](../../mfc/cwinapp-the-application-class.md).  
  
> [!NOTE]
>  Les applications MFC doivent être initialisées en tant que thread unique cloisonné (STA). Si vous appelez [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) dans votre `InitInstance` de remplacement, spécifiez `COINIT_APARTMENTTHREADED` (au lieu de `COINIT_MULTITHREADED`). Pour plus d’informations, consultez PRB : Application MFC cesse de répondre lors de l’initialisation de l’Application comme un multithread cloisonné (828643) à [http://support.microsoft.com/default.aspxscid=kb;en-us;828643](http://support.microsoft.com/default.aspxscid=kb;en-us;828643).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCListView&#9;](../../atl/reference/codesnippet/cpp/cwinapp-class_10.cpp)]  
  
##  <a name="a-nameistaskbarinteractionenableda--cwinappistaskbarinteractionenabled"></a><a name="istaskbarinteractionenabled"></a>CWinApp::IsTaskbarInteractionEnabled  
 Indique si l’interaction de la barre des tâches de Windows 7 est activée.  
  
```  
virtual BOOL IsTaskbarInteractionEnabled();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `TRUE` si `EnableTaskbarInteraction` a été appelé et le système d’exploitation est Windows 7 ou version ultérieure.  
  
### <a name="remarks"></a>Notes  
 Interaction de la barre des tâches signifie que les applications MDI affiche le contenu des enfants MDI dans les miniatures à onglets distincts qui s’affichent lorsque le pointeur de la souris est sur le bouton de la barre des tâches de l’application.  
  
##  <a name="a-nameloadcursora--cwinapploadcursor"></a><a name="loadcursor"></a>CWinApp::LoadCursor  
 Charge la ressource curseur nommée par `lpszResourceName` ou spécifié par `nIDResource` à partir du fichier exécutable en cours.  
  
```  
HCURSOR LoadCursor(LPCTSTR lpszResourceName) const;  HCURSOR LoadCursor(UINT nIDResource) const;  ```  
  
### Parameters  
 `lpszResourceName`  
 Points to a null-terminated string that contains the name of the cursor resource. You can use a `CString` for this argument.  
  
 `nIDResource`  
 ID of the cursor resource. For a list of resources, see [LoadCursor](http://msdn.microsoft.com/library/windows/desktop/ms648391) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Return Value  
 A handle to a cursor if successful; otherwise **NULL**.  
  
### Remarks  
 `LoadCursor` loads the cursor into memory only if it has not been previously loaded; otherwise, it retrieves a handle of the existing resource.  
  
 Use the [LoadStandardCursor](#loadstandardcursor) or [LoadOEMCursor](#loadoemcursor) member function to access the predefined Windows cursors.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#44](../../mfc/reference/codesnippet/cpp/cwinapp-class_11.cpp)]  
  
##  <a name="loadicon"></a>  CWinApp::LoadIcon  
 Loads the icon resource named by `lpszResourceName` or specified by `nIDResource` from the executable file.  
  
```  
LoadIcon(LPCTSTR lpszResourceName) HICON const ;  LoadIcon(UINT nIDResource) HICON const ;  ```  
  
### <a name="parameters"></a>Paramètres  
 `lpszResourceName`  
 Pointe vers une chaîne terminée par le caractère null qui contient le nom de la ressource d’icône. Vous pouvez également utiliser un `CString` pour cet argument.  
  
 `nIDResource`  
 Numéro d’identification de la ressource d’icône.  
  
### <a name="return-value"></a>Valeur de retour  
 Un handle d’une icône, en cas de réussite ; dans le cas contraire **NULL**.  
  
### <a name="remarks"></a>Remarques  
 `LoadIcon`charge l’icône uniquement si elle n'a pas été précédemment chargée ; dans le cas contraire, il récupère un handle de la ressource existante.  
  
 Vous pouvez utiliser la [LoadStandardIcon](#loadstandardicon) ou [LoadOEMIcon](#loadoemicon) fonction membre pour accéder aux icônes Windows prédéfinis.  
  
> [!NOTE]
>  Cette fonction membre appelle la fonction API Win32 [LoadIcon](http://msdn.microsoft.com/library/windows/desktop/ms648072), qui peut uniquement charger une icône dont la taille est conforme à la **SM_CXICON** et **SM_CYICON** valeurs métriques du système.  
  
##  <a name="a-nameloadoemcursora--cwinapploadoemcursor"></a><a name="loadoemcursor"></a>CWinApp::LoadOEMCursor  
 Charge les fenêtres prédéfinies ressource curseur spécifié par `nIDCursor`.  
  
```  
HCURSOR LoadOEMCursor(UINT nIDCursor) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nIDCursor`  
 Un **OCR_** manifeste identificateur constant qui spécifie un curseur Windows prédéfini. Vous devez avoir **#define OEMRESOURCE** avant **#include \<afxwin.h >** pour accéder à la **OCR_** constantes dans WINDOWS. H.  
  
### <a name="return-value"></a>Valeur de retour  
 Un handle à un curseur en cas de réussite ; dans le cas contraire **NULL**.  
  
### <a name="remarks"></a>Notes  
 Utilisez le `LoadOEMCursor` ou [LoadStandardCursor](#loadstandardcursor) fonction membre pour accéder aux curseurs Windows prédéfinis.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing n °&45;](../../mfc/reference/codesnippet/cpp/cwinapp-class_12.h)]  
  
 [!code-cpp[NVC_MFCWindowing&#46;](../../mfc/reference/codesnippet/cpp/cwinapp-class_13.cpp)]  
  
##  <a name="a-nameloadoemicona--cwinapploadoemicon"></a><a name="loadoemicon"></a>CWinApp::LoadOEMIcon  
 Charge les fenêtres prédéfinies ressource icône spécifiée par `nIDIcon`.  
  
```  
HICON LoadOEMIcon(UINT nIDIcon) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nIDIcon`  
 Un **OIC_** manifeste identificateur constant qui spécifie une icône Windows prédéfinie. Vous devez avoir **#define OEMRESOURCE** avant **#include \<afxwin.h >** pour accéder à la **OIC_** constantes dans WINDOWS. H.  
  
### <a name="return-value"></a>Valeur de retour  
 Un handle d’une icône, en cas de réussite ; dans le cas contraire **NULL**.  
  
### <a name="remarks"></a>Notes  
 Utilisez le `LoadOEMIcon` ou [LoadStandardIcon](#loadstandardicon) fonction membre pour accéder aux icônes Windows prédéfinis.  
  
##  <a name="a-nameloadstandardcursora--cwinapploadstandardcursor"></a><a name="loadstandardcursor"></a>CWinApp::LoadStandardCursor  
 Charge les fenêtres prédéfinies ressource curseur qui `lpszCursorName` spécifie.  
  
```  
HCURSOR LoadStandardCursor(LPCTSTR lpszCursorName) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszCursorName`  
 Un **IDC_** manifeste identificateur constant qui spécifie un curseur Windows prédéfini. Ces identificateurs sont définis dans WINDOWS. H. La liste suivante affiche les valeurs prédéfinies possibles et les significations pour `lpszCursorName`:  
  
- **IDC_ARROW** pointeur Standard  
  
- **IDC_IBEAM** curseur d’insertion de texte Standard  
  
- **IDC_WAIT** curseur sablier utilisé lorsque Windows exécute une tâche de longue durée  
  
- **IDC_CROSS** curseur croix pour la sélection  
  
- **IDC_UPARROW** flèche qui pointe vers le haut  
  
- **IDC_SIZE** obsolètes et non pris en charge ; utilisez **IDC_SIZEALL**  
  
- **IDC_SIZEALL** une flèche à quatre pointes. Le curseur à utiliser pour redimensionner une fenêtre.  
  
- **IDC_ICON** obsolètes et non pris en charge. Utilisez **IDC_ARROW**.  
  
- **IDC_SIZENWSE** flèche à deux pointes avec se terminant à l’angle supérieur gauche et inférieur droit  
  
- **IDC_SIZENESW** flèche à deux pointes avec se terminant à l’angle supérieur gauche à droite et inférieure  
  
- **IDC_SIZEWE** flèche à deux pointes horizontale  
  
- **IDC_SIZENS** verticale double flèche  
  
### <a name="return-value"></a>Valeur de retour  
 Un handle à un curseur en cas de réussite ; dans le cas contraire **NULL**.  
  
### <a name="remarks"></a>Remarques  
 Utilisez le `LoadStandardCursor` ou [LoadOEMCursor](#loadoemcursor) fonction membre pour accéder aux curseurs Windows prédéfinis.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#47;](../../mfc/reference/codesnippet/cpp/cwinapp-class_14.cpp)]  
  
##  <a name="a-nameloadstandardicona--cwinapploadstandardicon"></a><a name="loadstandardicon"></a>CWinApp::LoadStandardIcon  
 Charge les fenêtres prédéfinies ressource icône qui `lpszIconName` spécifie.  
  
```  
HICON LoadStandardIcon(LPCTSTR lpszIconName) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszIconName`  
 Un identificateur constant manifest qui spécifie une icône Windows prédéfinie. Ces identificateurs sont définis dans WINDOWS. H. Pour obtenir la liste des valeurs possibles prédéfinies et leurs descriptions, consultez la *lpIconName* paramètre [LoadIcon](http://msdn.microsoft.com/library/windows/desktop/ms648072) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Valeur de retour  
 Un handle d’une icône, en cas de réussite ; dans le cas contraire **NULL**.  
  
### <a name="remarks"></a>Remarques  
 Utilisez le `LoadStandardIcon` ou [LoadOEMIcon](#loadoemicon) fonction membre pour accéder aux icônes Windows prédéfinis.  
  
##  <a name="a-nameloadstdprofilesettingsa--cwinapploadstdprofilesettings"></a><a name="loadstdprofilesettings"></a>CWinApp::LoadStdProfileSettings  
 Appelez cette fonction membre depuis le [InitInstance](#initinstance) fonction membre activer et de charger la liste des fichiers les plus récemment utilisés (MRU) et de prévisualiser dernier état.  
  
```  
void LoadStdProfileSettings(UINT nMaxMRU = _AFX_MRU_COUNT);
```  
  
### <a name="parameters"></a>Paramètres  
 `nMaxMRU`  
 Le nombre de fichiers récemment utilisés pour effectuer le suivi.  
  
### <a name="remarks"></a>Remarques  
 Si `nMaxMRU` est 0, aucune liste des derniers fichiers utilisés n’est conservé.  
  
##  <a name="a-namembhelpmodea--cwinappmbhelpmode"></a><a name="m_bhelpmode"></a>CWinApp::m_bHelpMode  
 **TRUE** si l’application est en mode de contexte d’aide (traditionnellement appelé avec MAJ + F1) ; sinon **FALSE**.  
  
```  
BOOL m_bHelpMode;  
```  
  
### <a name="remarks"></a>Notes  
 En mode de contexte d’aide, le curseur se transforme en un point d’interrogation et l’utilisateur peut le déplacer sur l’écran. Examinez cet indicateur si vous souhaitez mettre en œuvre un traitement spécial dans le mode d’aide. `m_bHelpMode`est une variable publique de type **BOOL**.  
  
##  <a name="a-namemdwrestartmanagersupportflagsa--cwinappmdwrestartmanagersupportflags"></a><a name="m_dwrestartmanagersupportflags"></a>CWinApp::m_dwRestartManagerSupportFlags  
 Indicateurs qui déterminent le comportement du Gestionnaire de redémarrage.  
  
```  
DWORD m_dwRestartManagerSupportFlags;  
```  
  
### <a name="remarks"></a>Remarques  
 Pour activer le Gestionnaire de redémarrage, définissez `m_dwRestartManagerSupportFlags` au comportement souhaité. Le tableau suivant montre les indicateurs qui sont disponibles.  
  
|||  
|-|-|  
|Indicateur|Description|  
|`AFX_RESTART_MANAGER_SUPPORT_RESTART`|L’application est inscrite à l’aide de [CWinApp::RegisterWithRestartManager](#registerwithrestartmanager). Le Gestionnaire de redémarrage est chargé pour le redémarrage de l’application si elle ferme de façon inattendue.|  
|- `AFX_RESTART_MANAGER_SUPPORT_RECOVERY`|L’application est inscrite avec le Gestionnaire de redémarrage, le Gestionnaire de redémarrage appelle la fonction de rappel de récupération lorsqu’elle redémarre l’application. La fonction de rappel de récupération par défaut est [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).|  
|- `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART`|Enregistrement automatique est activé et le Gestionnaire de redémarrage enregistre automatiquement les documents ouverts lorsque l’application redémarre.|  
|- `AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL`|Enregistrement automatique est activé et le Gestionnaire de redémarrage enregistre automatiquement les documents ouverts à intervalles réguliers. L’intervalle est défini par [CWinApp::m_nAutosaveInterval](#m_nautosaveinterval).|  
|- `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`|Le Gestionnaire de redémarrage ouvre des documents précédemment ouverts après le redémarrage de l’application à partir d’une sortie inattendue. Le [CDataRecoveryHandler classe](../../mfc/reference/cdatarecoveryhandler-class.md) gère le stockage de la liste des documents ouverts et de leur restauration.|  
|- `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES`|Le Gestionnaire de redémarrage invite l’utilisateur à restaurer les fichiers enregistrée automatiquement après le redémarrage de l’application. La `CDataRecoveryHandler` classe interroge l’utilisateur.|  
|- `AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE`|L’union de `AFX_RESTART_MANAGER_SUPPORT_RESTART`, `AFX_RESTART_MANAGER_SUPPORT_RECOVER`, et `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`.|  
|- `AFX_RESTART_MANAGER_SUPPORT_ALL_ASPECTS`|The union of `AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE`, `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART`, `AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL`, and `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES`.|  
|- `AFX_RESTART_MANAGER_SUPPORT_RESTART_ASPECTS`|The union of `AFX_RESTART_MANAGER_SUPPORT_RESTART`, `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART`, `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`, and `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES`.|  
|- `AFX_RESTART_MANAGER_SUPPORT_RECOVERY_ASPECTS`|The union of `AFX_RESTART_MANAGER_SUPPORT_RECOVERY`, `AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL`, `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`, and `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES`.|  
  
##  <a name="a-namemehelptypea--cwinappmehelptype"></a><a name="m_ehelptype"></a>CWinApp::m_eHelpType  
 Le type de ce membre de données est le type énuméré **AFX_HELP_TYPE**, qui est défini dans la `CWinApp` classe.  
  
```  
AFX_HELP_TYPE m_eHelpType;  
```  
  
### <a name="remarks"></a>Remarques  
 Le **AFX_HELP_TYPE** énumération est définie comme suit :  
  
 `enum AFX_HELP_TYPE`  
  
 `{`  
  
 `afxWinHelp = 0,`  
  
 `afxHTMLHelp = 1`  
  
 `};`  
  
-   Pour définir l’aide de l’application à l’aide HTML, appelez [SetHelpMode](#sethelpmode) et spécifiez **afxHTMLHelp**.  
  
-   Pour définir l’aide de l’application à WinHelp, appelez `SetHelpMode` et spécifiez **afxWinHelp**.  
  
##  <a name="a-namemhinstancea--cwinappmhinstance"></a><a name="m_hinstance"></a>CWinApp::m_hInstance  
 Correspond à la `hInstance` paramètre passé par Windows pour `WinMain`.  
  
```  
HINSTANCE m_hInstance;  
```  
  
### <a name="remarks"></a>Remarques  
 Le `m_hInstance` membre de données est un handle vers l’instance actuelle de l’application s’exécutant sous Windows. Ceci est retourné par la fonction globale [AfxGetInstanceHandle](application-information-and-management.md#afxgetinstancehandle). `m_hInstance`est une variable publique de type `HINSTANCE`.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#55;](../../mfc/reference/codesnippet/cpp/cwinapp-class_15.cpp)]  
  
##  <a name="a-namemlpcmdlinea--cwinappmlpcmdline"></a><a name="m_lpcmdline"></a>CWinApp::m_lpCmdLine  
 Correspond à la `lpCmdLine` paramètre passé par Windows pour `WinMain`.  
  
```  
LPTSTR m_lpCmdLine;  
```  
  
### <a name="remarks"></a>Remarques  
 Pointe vers une chaîne terminée par le caractère null qui spécifie la ligne de commande pour l’application. Utilisez `m_lpCmdLine` pour accéder à tous les arguments de ligne de commande entrées lorsque l’application a été démarrée par l’utilisateur. `m_lpCmdLine`est une variable publique de type `LPTSTR`.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#52;](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]  
  
##  <a name="a-namemnautosaveintervala--cwinappmnautosaveinterval"></a><a name="m_nautosaveinterval"></a>CWinApp::m_nAutosaveInterval  
 La durée en millisecondes entre enregistre automatiquement.  
  
```  
int m_nAutosaveInterval;  
```  
  
### <a name="remarks"></a>Remarques  
 Vous pouvez configurer le Gestionnaire de redémarrage pour l’enregistrement automatique des documents ouverts à des intervalles définis. Si votre application ne pas les fichiers d’enregistrement automatique, ce paramètre n’a aucun effet.  
  
##  <a name="a-namemncmdshowa--cwinappmncmdshow"></a><a name="m_ncmdshow"></a>CWinApp::m_nCmdShow  
 Correspond à la `nCmdShow` paramètre passé par Windows pour `WinMain`.  
  
```  
int m_nCmdShow;  
```  
  
### <a name="remarks"></a>Remarques  
 Vous devez passer `m_nCmdShow` en tant qu’argument lorsque vous appelez [CWnd::ShowWindow](../../mfc/reference/cwnd-class.md#showwindow) pour la fenêtre principale de votre application. `m_nCmdShow`est une variable publique de type `int`.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#56;](../../mfc/reference/codesnippet/cpp/cwinapp-class_17.cpp)]  
  
##  <a name="a-namempactivewnda--cwinappmpactivewnd"></a><a name="m_pactivewnd"></a>CWinApp::m_pActiveWnd  
 Utilisez ce membre de données pour stocker un pointeur vers la fenêtre principale de l’application de conteneur OLE qui a votre OLE serveur application activé sur place.  
  
### <a name="remarks"></a>Remarques  
 Si ce membre de données est **NULL**, l’application n’est pas actif en place.  
  
 L’infrastructure définit cette variable membre lorsque la fenêtre frame est activé par une application conteneur OLE sur place.  
  
##  <a name="a-namempdatarecoveryhandlera--cwinappmpdatarecoveryhandler"></a><a name="m_pdatarecoveryhandler"></a>CWinApp::m_pDataRecoveryHandler  
 Pointeur vers le Gestionnaire de récupération de données pour l’application.  
  
```  
CDataRecoveryHandler* m_pDataRecoveryHandler;  
```  
  
### <a name="remarks"></a>Remarques  
 Le Gestionnaire de récupération de données d’une application analyse les documents ouverts et enregistre automatiquement les. L’infrastructure utilise le Gestionnaire de récupération de données pour restaurer les fichiers d’enregistrée automatiquement lorsqu’une application redémarre après sa sortie de façon inattendue. Pour plus d’informations, consultez [CDataRecoveryHandler classe](../../mfc/reference/cdatarecoveryhandler-class.md).  
  
##  <a name="a-namempszappnamea--cwinappmpszappname"></a><a name="m_pszappname"></a>CWinApp::m_pszAppName  
 Spécifie le nom de l’application.  
  
```  
LPCTSTR m_pszAppName;  
```  
  
### <a name="remarks"></a>Remarques  
 Le nom de l’application peut provenir du paramètre transmis à la [CWinApp](#cwinapp) constructeur, ou, si non spécifié, à la chaîne de ressource avec l’ID de **AFX_IDS_APP_TITLE**. Si le nom de l’application est introuvable dans la ressource, il est fourni à partir du programme. Nom du fichier EXE.  
  
 Retourné par la fonction globale [AfxGetAppName](application-information-and-management.md#afxgetappname). `m_pszAppName`est une variable publique de type **const char\***.  
  
> [!NOTE]
>  Si vous attribuez une valeur à `m_pszAppName`, il doit être dynamiquement alloué sur le tas. Le `CWinApp` destructeur appelle **libre**() avec ce pointeur. Nombreuses voulez-vous utiliser la `_tcsdup`fonction de bibliothèque Runtime () pour effectuer l’allocation. En outre, libérer la mémoire associée au pointeur en cours avant d’attribuer une nouvelle valeur. Exemple :  
  
 [!code-cpp[NVC_MFCWindowing&#57;](../../mfc/reference/codesnippet/cpp/cwinapp-class_18.cpp)]  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#65;](../../mfc/reference/codesnippet/cpp/cwinapp-class_19.cpp)]  
  
##  <a name="a-namempszexenamea--cwinappmpszexename"></a><a name="m_pszexename"></a>CWinApp::m_pszExeName  
 Contient le nom du fichier exécutable de l’application sans extension.  
  
```  
LPCTSTR m_pszExeName;  
```  
  
### <a name="remarks"></a>Notes  
 Contrairement aux [m_pszAppName](#m_pszappname), ce nom ne peut pas contenir d’espaces. `m_pszExeName`est une variable publique de type **const char\***.  
  
> [!NOTE]
>  Si vous attribuez une valeur à `m_pszExeName`, il doit être dynamiquement alloué sur le tas. Le `CWinApp` destructeur appelle **libre**() avec ce pointeur. Nombreuses voulez-vous utiliser la `_tcsdup`fonction de bibliothèque Runtime () pour effectuer l’allocation. En outre, libérer la mémoire associée au pointeur en cours avant d’attribuer une nouvelle valeur. Exemple :  
  
 [!code-cpp[NVC_MFCWindowing&#58;](../../mfc/reference/codesnippet/cpp/cwinapp-class_20.cpp)]  
  
##  <a name="a-namempszhelpfilepatha--cwinappmpszhelpfilepath"></a><a name="m_pszhelpfilepath"></a>CWinApp::m_pszHelpFilePath  
 Contient le chemin d’accès au fichier d’aide de l’application.  
  
```  
LPCTSTR m_pszHelpFilePath;  
```  
  
### <a name="remarks"></a>Notes  
 Par défaut, le framework initialise `m_pszHelpFilePath` au nom de l’application ». HLP » ajouté. Pour modifier le nom du fichier d’aide, définissez `m_pszHelpFilePath` pour pointer vers une chaîne qui contient le nom complet du fichier d’aide souhaitée. Pour cela est pratique dans l’application [InitInstance](#initinstance) (fonction). `m_pszHelpFilePath`est une variable publique de type **const char\***.  
  
> [!NOTE]
>  Si vous attribuez une valeur à `m_pszHelpFilePath`, il doit être dynamiquement alloué sur le tas. Le `CWinApp` destructeur appelle **libre**() avec ce pointeur. Nombreuses voulez-vous utiliser la `_tcsdup`fonction de bibliothèque Runtime () pour effectuer l’allocation. En outre, libérer la mémoire associée au pointeur en cours avant d’attribuer une nouvelle valeur. Exemple :  
  
 [!code-cpp[NVC_MFCWindowing&#59;](../../mfc/reference/codesnippet/cpp/cwinapp-class_21.cpp)]  
  
##  <a name="a-namempszprofilenamea--cwinappmpszprofilename"></a><a name="m_pszprofilename"></a>CWinApp::m_pszProfileName  
 Contient le nom de l’application. Fichier INI.  
  
```  
LPCTSTR m_pszProfileName;  
```  
  
### <a name="remarks"></a>Remarques  
 `m_pszProfileName`est une variable publique de type **const char\***.  
  
> [!NOTE]
>  Si vous attribuez une valeur à `m_pszProfileName`, il doit être dynamiquement alloué sur le tas. Le `CWinApp` destructeur appelle **libre**() avec ce pointeur. Nombreuses voulez-vous utiliser la `_tcsdup`fonction de bibliothèque Runtime () pour effectuer l’allocation. En outre, libérer la mémoire associée au pointeur en cours avant d’attribuer une nouvelle valeur. Exemple :  
  
 [!code-cpp[NVC_MFCWindowing&#60;](../../mfc/reference/codesnippet/cpp/cwinapp-class_22.cpp)]  
  
##  <a name="a-namempszregistrykeya--cwinappmpszregistrykey"></a><a name="m_pszregistrykey"></a>CWinApp::m_pszRegistryKey  
 Utilisé pour déterminer où, dans le Registre ou le fichier INI, les paramètres de profil d’application sont stockés.  
  
```  
LPCTSTR m_pszRegistryKey;  
```  
  
### <a name="remarks"></a>Remarques  
 Normalement, ce membre de données est traité en lecture seule.  
  
-   La valeur est stockée dans une clé de Registre. Le nom du paramètre de profil d’application est ajouté à la clé de Registre suivante : HKEY_CURRENT_USER / / LocalAppWizard générées par les logiciels /.  
  
 Si vous attribuez une valeur à `m_pszRegistryKey`, il doit être dynamiquement alloué sur le tas. Le `CWinApp` destructeur appelle **libre**() avec ce pointeur. Nombreuses voulez-vous utiliser la `_tcsdup`fonction de bibliothèque Runtime () pour effectuer l’allocation. En outre, libérer la mémoire associée au pointeur en cours avant d’attribuer une nouvelle valeur. Exemple :  
  
 [!code-cpp[NVC_MFCWindowing&#61;](../../mfc/reference/codesnippet/cpp/cwinapp-class_23.cpp)]  
  
##  <a name="a-namempszappida--cwinappmpszappid"></a><a name="m_pszappid"></a>CWinApp::m_pszAppID  
 ID du modèle application utilisateur.  
  
```  
LPCTSTR m_pszAppID;  
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameoncontexthelpa--cwinapponcontexthelp"></a><a name="oncontexthelp"></a>CWinApp::OnContextHelp  
 Gère MAJ + F1 dans l’application.  
  
```  
afx_msg void OnContextHelp();
```  
  
### <a name="remarks"></a>Remarques  
 Vous devez ajouter un `ON_COMMAND( ID_CONTEXT_HELP, OnContextHelp )` instruction à votre `CWinApp` classe table des messages et ajouter une entrée de table d’accélérateurs, généralement MAJ + F1, pour activer cette fonction membre.  
  
 `OnContextHelp`met l’application en mode d’aide. Le curseur se transforme en flèche et un point d’interrogation et que l’utilisateur peut déplacer le pointeur de la souris, puis appuyez sur le bouton gauche de la souris pour sélectionner une boîte de dialogue, une fenêtre, un menu ou un bouton de commande. Cette fonction membre récupère le contexte d’aide de l’objet sous le curseur et appelle la fonction Windows WinHelp avec ce contexte d’aide.  
  
##  <a name="a-nameonddecommanda--cwinapponddecommand"></a><a name="onddecommand"></a>CWinApp::OnDDECommand  
 Appelé par l’infrastructure lorsque la fenêtre frame principale reçoit DDE d’exécuter.  
  
```  
virtual BOOL OnDDECommand(LPTSTR lpszCommand);
```  
  
### <a name="parameters"></a>Paramètres  
 *lpszCommand*  
 Pointe vers une chaîne de commande DDE reçu par l’application.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la commande est gérée ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 L’implémentation par défaut vérifie si la commande est une demande d’ouverture d’un document et, si tel est le cas, ouvre le document spécifié. Le Gestionnaire de fichiers Windows envoie généralement ces chaînes de commande DDE lorsque l’utilisateur double-clique sur un fichier de données. Remplacement de cette fonction pour gérer les autres DDE exécuter des commandes, telles que la commande Imprimer.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#48;](../../mfc/reference/codesnippet/cpp/cwinapp-class_24.cpp)]  
  
##  <a name="a-nameonfilenewa--cwinapponfilenew"></a><a name="onfilenew"></a>CWinApp::OnFileNew  
 Implémente la `ID_FILE_NEW` commande.  
  
```  
afx_msg void OnFileNew();
```  
  
### <a name="remarks"></a>Remarques  
 Vous devez ajouter un `ON_COMMAND( ID_FILE_NEW, OnFileNew )` instruction à votre `CWinApp` table des messages pour activer cette fonction membre de classe. S’il est activé, cette fonction gère l’exécution de la commande fichier nouveau.  
  
 Consultez la page [Note technique 22](../../mfc/tn022-standard-commands-implementation.md) pour plus d’informations sur le comportement par défaut et des conseils sur le remplacement de cette fonction membre.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[49 NVC_MFCWindowing](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing&#50;](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]  
  
##  <a name="a-nameonfileopena--cwinapponfileopen"></a><a name="onfileopen"></a>CWinApp::OnFileOpen  
 Implémente la `ID_FILE_OPEN` commande.  
  
```  
afx_msg void OnFileOpen();
```  
  
### <a name="remarks"></a>Remarques  
 Vous devez ajouter un `ON_COMMAND( ID_FILE_OPEN, OnFileOpen )` instruction à votre `CWinApp` table des messages pour activer cette fonction membre de classe. S’il est activé, cette fonction gère l’exécution de la commande Ouvrir un fichier.  
  
 Pour plus d’informations sur le comportement par défaut et des conseils sur le remplacement de cette fonction membre, consultez [Note technique 22](../../mfc/tn022-standard-commands-implementation.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[49 NVC_MFCWindowing](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing&#50;](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]  
  
##  <a name="a-nameonfileprintsetupa--cwinapponfileprintsetup"></a><a name="onfileprintsetup"></a>CWinApp::OnFilePrintSetup  
 Implémente le **ID_FILE_PRINT_SETUP** commande.  
  
```  
afx_msg void OnFilePrintSetup();
```  
  
### <a name="remarks"></a>Remarques  
 Vous devez ajouter un `ON_COMMAND( ID_FILE_PRINT_SETUP, OnFilePrintSetup )` instruction à votre `CWinApp` table des messages pour activer cette fonction membre de classe. S’il est activé, cette fonction gère l’exécution de la commande Imprimer du fichier.  
  
 Pour plus d’informations sur le comportement par défaut et des conseils sur le remplacement de cette fonction membre, consultez [Note technique 22](../../mfc/tn022-standard-commands-implementation.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[49 NVC_MFCWindowing](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing&#50;](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]  
  
##  <a name="a-nameonhelpa--cwinapponhelp"></a><a name="onhelp"></a>CWinApp::OnHelp  
 Gère l'aide F1 dans l'application (en utilisant le contexte actuel).  
  
```  
afx_msg void OnHelp();
```  
  
### <a name="remarks"></a>Remarques  
 En général, vous ajouterez également une entrée de touche d’accès rapide pour la touche F1. L’activation de la touche F1 est uniquement une convention, n’est pas obligatoire.  
  
 Vous devez ajouter un `ON_COMMAND( ID_HELP, OnHelp )` instruction à votre `CWinApp` table des messages pour activer cette fonction membre de classe. S’il est activé, appelée par l’infrastructure lorsque l’utilisateur appuie sur la touche F1.  
  
 L’implémentation par défaut de cette fonction de gestionnaire de messages détermine le contexte d’aide qui correspond à la fenêtre active, une boîte de dialogue ou un élément de menu, puis appelle WINHELP. EXE. Si aucun contexte n’est disponible, la fonction utilise le contexte par défaut.  
  
 Remplacez cette fonction membre pour définir le contexte d’aide pour un élément autre que la fenêtre, une boîte de dialogue, un élément de menu ou un bouton de barre d’outils qui a actuellement le focus. Appelez `WinHelp` avec l’aide d’ID de contexte.  
  
##  <a name="a-nameonhelpfindera--cwinapponhelpfinder"></a><a name="onhelpfinder"></a>CWinApp::OnHelpFinder  
 Gère la **ID_HELP_FINDER** et **ID_DEFAULT_HELP** commandes.  
  
```  
afx_msg void OnHelpFinder();
```  
  
### <a name="remarks"></a>Remarques  
 Vous devez ajouter un `ON_COMMAND( ID_HELP_FINDER, OnHelpFinder )` instruction à votre `CWinApp` table des messages pour activer cette fonction membre de classe. S’il est activé, l’infrastructure appelle cette fonction gestionnaire de messages lorsque l’utilisateur de votre application sélectionne la commande de recherche d’aide pour appeler `WinHelp` avec la norme **HELP_FINDER** rubrique.  
  
##  <a name="a-nameonhelpindexa--cwinapponhelpindex"></a><a name="onhelpindex"></a>CWinApp::OnHelpIndex  
 Gère la **ID_HELP_INDEX** de commande et fournit une rubrique d’aide par défaut.  
  
```  
afx_msg void OnHelpIndex();
```  
  
### <a name="remarks"></a>Remarques  
 Vous devez ajouter un `ON_COMMAND( ID_HELP_INDEX, OnHelpIndex )` instruction à votre `CWinApp` table des messages pour activer cette fonction membre de classe. S’il est activé, l’infrastructure appelle cette fonction gestionnaire de messages lorsque l’utilisateur de votre application sélectionne la commande de l’Index d’aide pour appeler `WinHelp` avec la norme **HELP_INDEX** rubrique.  
  
##  <a name="a-nameonhelpusinga--cwinapponhelpusing"></a><a name="onhelpusing"></a>CWinApp::OnHelpUsing  
 Gère la **ID_HELP_USING** commande.  
  
```  
afx_msg void OnHelpUsing();
```  
  
### <a name="remarks"></a>Remarques  
 Vous devez ajouter un `ON_COMMAND( ID_HELP_USING, OnHelpUsing )` instruction à votre `CWinApp` table des messages pour activer cette fonction membre de classe. L’infrastructure appelle cette fonction gestionnaire de messages lorsque l’utilisateur de votre application sélectionne la commande aide à l’aide pour appeler le `WinHelp` application avec la norme **HELP_HELPONHELP** rubrique.  
  
##  <a name="a-nameonidlea--cwinapponidle"></a><a name="onidle"></a>CWinApp::OnIdle  
 Remplacez cette fonction membre pour effectuer le traitement des temps d’inactivité.  
  
```  
virtual BOOL OnIdle(LONG lCount);
```  
  
### <a name="parameters"></a>Paramètres  
 `lCount`  
 Un compteur incrémenté chaque fois que `OnIdle` est appelé lorsque la file d’attente de messages de l’application est vide. Ce compteur est réinitialisé à 0 à chaque fois qu’un nouveau message est traité. Vous pouvez utiliser la `lCount` paramètre pour déterminer la durée relative de l’application a été inactive sans le traitement d’un message.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro pour recevoir plus le temps de traitement inactif ; 0 si plus aucun temps d’inactivité est nécessaire.  
  
### <a name="remarks"></a>Remarques  
 `OnIdle`est appelée dans la boucle de message par défaut lors de la file d’attente de messages de l’application est vide. Utilisez votre remplacement pour appeler votre propre expérience de tâches du Gestionnaire d’inactivité.  
  
 `OnIdle`Renvoie 0 pour indiquer qu’aucun temps de traitement inactif n’est requis. Le `lCount` paramètre est incrémenté chaque fois que `OnIdle` est appelé lorsque la file d’attente est vide et réinitialise à 0, chaque fois qu’un nouveau message est traité. Vous pouvez appeler vos routines d’inactivité différents en fonction de ce nombre.  
  
 Traitement des boucles inactives sont récapitulés ci-dessous :  
  
1.  Si la boucle de message dans la bibliothèque Microsoft Foundation Class vérifie la file d’attente et ne recherche les messages en attente, elle appelle `OnIdle` pour l’objet application et les fournitures 0 comme le `lCount` argument.  
  
2. `OnIdle`effectue un traitement et retourne une valeur différente de zéro pour indiquer qu’il doit encore être appelée pour effectuer un traitement supplémentaire.  
  
3.  La boucle de message vérifie à nouveau la file d’attente. Si aucun message n’est en attente, elle appelle `OnIdle` , incrémentant le `lCount` argument.  
  
4.  Finalement, `OnIdle` a terminé le traitement de toutes ses tâches inactifs et retourne 0. Cela indique à la boucle de message cesse d’appeler `OnIdle` avant la réception du message suivant de la file d’attente, auquel cas le cycle inactif redémarre avec l’argument défini à 0.  
  
 N’effectuez pas de tâches de longue durée au cours de `OnIdle` , car votre application ne peut pas traiter l’entrée d’utilisateur jusqu'à ce que `OnIdle` retourne.  
  
> [!NOTE]
>  L’implémentation par défaut de `OnIdle` mises à jour des objets d’interface utilisateur tels que les éléments de menu et boutons de barre d’outils de commande et il exécute un nettoyage de structure de données interne. Par conséquent, si vous substituez `OnIdle`, vous devez appeler `CWinApp::OnIdle` avec la `lCount` dans la version substituée. Traitement inactif de classe de base tout d’abord appeler (c'est-à-dire, jusqu'à ce que la classe de base `OnIdle` renvoie la valeur 0). Si vous avez besoin effectuer le travail avant la fin du traitement de la classe de base, examinez l’implémentation de classe de base pour sélectionner correct `lCount` au cours de laquelle effectuer votre travail.  
  
 Si vous ne souhaitez pas `OnIdle` pour être appelée chaque fois qu’un message est récupéré à partir de la file d’attente, vous pouvez remplacer le [CWinThreadIsIdleMessage](../../mfc/reference/cwinthread-class.md#isidlemessage). Si une application a défini un minuteur très court, ou si le système envoie la **WM_SYSTIMER** d’un message, puis `OnIdle` sera appelée à plusieurs reprises et dégrader les performances.  
  
### <a name="example"></a>Exemple  
 Les deux exemples suivants montrent comment utiliser `OnIdle`. Le premier exemple traite deux tâches inactives à l’aide de la `lCount` argument afin de hiérarchiser les tâches. La première tâche consiste à priorité élevée, et vous devez le faire dès que possible. La seconde tâche est moins importante et doit être effectuée uniquement s’il existe une longue pause dans l’entrée d’utilisateur. Notez l’appel à la version de classe de base de `OnIdle`. Le deuxième exemple gère un groupe de tâches inactives avec des priorités différentes.  
  
 [!code-cpp[NVC_MFCWindowing&#51;](../../mfc/reference/codesnippet/cpp/cwinapp-class_27.cpp)]  
  
##  <a name="a-nameopendocumentfilea--cwinappopendocumentfile"></a><a name="opendocumentfile"></a>CWinApp::OpenDocumentFile  
 L’infrastructure appelle cette méthode pour ouvrir l’index nommé [CDocument](../../mfc/reference/cdocument-class.md) fichier de l’application.  
  
```  
virtual CDocument* OpenDocumentFile(
LPCTSTR lpszFileName  
BOOL bAddToMRU = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszFileName`  
 Le nom du fichier à ouvrir.  
  
 [in] `bAddToMRU`  
 `TRUE`Indique que le document est un des fichiers plus récents ; `FALSE` indique le document n’est pas un des fichiers plus récents.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un `CDocument` cas de réussite ; sinon `NULL`.  
  
### <a name="remarks"></a>Remarques  
 Si un document portant ce nom est déjà ouvert, la première fenêtre frame contenant ce document obtenez le focus. Si une application prend en charge plusieurs modèles de document, l’infrastructure utilise l’extension de nom de fichier pour rechercher le modèle de document approprié à essayer de charger le document. Si l’opération réussit, le modèle de document crée ensuite une fenêtre frame et la vue du document.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#52;](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]  
  
##  <a name="a-nameparsecommandlinea--cwinappparsecommandline"></a><a name="parsecommandline"></a>CWinApp::ParseCommandLine  
 Appelez cette fonction membre pour analyser la ligne de commande et d’envoyer les paramètres à la fois, à [CCommandLineInfo::ParseParam](../../mfc/reference/ccommandlineinfo-class.md#parseparam).  
  
```  
void ParseCommandLine(CCommandLineInfo& rCmdInfo);
```  
  
### <a name="parameters"></a>Paramètres  
 `rCmdInfo`  
 Une référence à un [CCommandLineInfo](../../mfc/reference/ccommandlineinfo-class.md) objet.  
  
### <a name="remarks"></a>Notes  
 Lorsque vous démarrez un nouveau projet MFC à l’aide de l’Assistant Application, l’Assistant Application crée une instance locale de `CCommandLineInfo`, puis appelez `ProcessShellCommand` et `ParseCommandLine` dans les [InitInstance](#initinstance) fonction membre. Une ligne de commande suit l’itinéraire décrite ci-dessous :  
  
1.  Après avoir été créé dans `InitInstance`, le `CCommandLineInfo` objet est passé à `ParseCommandLine`.  
  
2. `ParseCommandLine`appelle ensuite `CCommandLineInfo::ParseParam` à plusieurs reprises, une fois pour chaque paramètre.  
  
3. `ParseParam`remplit le `CCommandLineInfo` objet, qui est ensuite transmis à [ProcessShellCommand](#processshellcommand).  
  
4. `ProcessShellCommand`gère les arguments de ligne de commande et les indicateurs.  
  
 Notez que vous pouvez appeler `ParseCommandLine` directement en fonction des besoins.  
  
 Pour obtenir une description des indicateurs de ligne de commande, consultez la page [CCommandLineInfo::m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand).  
  
##  <a name="a-namepretranslatemessagea--cwinapppretranslatemessage"></a><a name="pretranslatemessage"></a>CWinApp::PreTranslateMessage  
 Remplacez cette fonction pour filtrer les messages de fenêtre avant leur distribution aux fonctions Windows [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) et [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) l’implémentation par défaut effectue la traduction de la touche d’accès rapide, vous devez appeler le `CWinApp::PreTranslateMessage` fonction membre dans votre version substituée.  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Paramètres  
 `pMsg`  
 Un pointeur vers un [MSG](../../mfc/reference/msg-structure1.md) structure qui contient le message à traiter.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le message a été entièrement traité dans `PreTranslateMessage` et ne doit pas être traitée ultérieurement. Zéro si le message doit être traité de façon normale.  
  
##  <a name="a-nameprocessmessagefiltera--cwinappprocessmessagefilter"></a><a name="processmessagefilter"></a>CWinApp::ProcessMessageFilter  
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
 Un pointeur vers un Windows [MSG](../../mfc/reference/msg-structure1.md) structure.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le message est traité ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Une fonction de raccordement traite les événements avant de les envoyer à un message normal de l’application de traitement.  
  
 Si vous substituez cette fonctionnalité avancée, veillez à appeler la version classe de base pour maintenir l’infrastructure de raccordement de traitement.  
  
##  <a name="a-nameprocessshellcommanda--cwinappprocessshellcommand"></a><a name="processshellcommand"></a>CWinApp::ProcessShellCommand  
 Cette fonction membre est appelée par [InitInstance](#initinstance) pour accepter les paramètres transmis à partir de la `CCommandLineInfo` objet identifié par `rCmdInfo`et exécuter l’action indiquée.  
  
```  
BOOL ProcessShellCommand(CCommandLineInfo& rCmdInfo);
```  
  
### <a name="parameters"></a>Paramètres  
 `rCmdInfo`  
 Une référence à un [CCommandLineInfo](../../mfc/reference/ccommandlineinfo-class.md) objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la commande shell est traitée avec succès. Retourne la valeur 0, **FALSE** de [InitInstance](#initinstance).  
  
### <a name="remarks"></a>Notes  
 Lorsque vous démarrez un nouveau projet MFC à l’aide de l’Assistant Application, l’Assistant Application crée une instance locale de `CCommandLineInfo`, puis appelez `ProcessShellCommand` et [ParseCommandLine](#parsecommandline) dans les `InitInstance` fonction membre. Une ligne de commande suit l’itinéraire décrite ci-dessous :  
  
1.  Après avoir été créé dans `InitInstance`, le `CCommandLineInfo` objet est passé à `ParseCommandLine`.  
  
2. `ParseCommandLine`appelle ensuite [CCommandLineInfo::ParseParam](../../mfc/reference/ccommandlineinfo-class.md#parseparam) à plusieurs reprises, une fois pour chaque paramètre.  
  
3. `ParseParam`remplit le `CCommandLineInfo` objet, qui est ensuite transmis à `ProcessShellCommand`.  
  
4. `ProcessShellCommand`gère les arguments de ligne de commande et les indicateurs.  
  
 Les membres de données de la `CCommandLineInfo` objet, identifié par [CCommandLineInfo::m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand), sont du type énuméré suivant, qui est défini dans la `CCommandLineInfo` classe.  
  
 `enum {`  
  
 `FileNew,`  
  
 `FileOpen,`  
  
 `FilePrint,`  
  
 `FilePrintTo,`  
  
 `FileDDE,`  
  
 `};`  
  
 Pour obtenir une brève description de chacune de ces valeurs, consultez la page `CCommandLineInfo::m_nShellCommand`.  
  
##  <a name="a-nameprocesswndprocexceptiona--cwinappprocesswndprocexception"></a><a name="processwndprocexception"></a>CWinApp::ProcessWndProcException  
 L’infrastructure appelle cette fonction membre, chaque fois que le gestionnaire n’intercepte pas une exception levée dans un des messages de votre application ou les gestionnaires de commandes.  
  
```  
virtual LRESULT ProcessWndProcException(
    CException* e,  
    const MSG* pMsg);
```  
  
### <a name="parameters"></a>Paramètres  
 *e*  
 Pointeur vers une exception non interceptée.  
  
 `pMsg`  
 A [MSG](../../mfc/reference/msg-structure1.md) structure qui contient des informations sur le message windows qui a provoqué le framework lève une exception.  
  
### <a name="return-value"></a>Valeur de retour  
 La valeur doit être retournée à Windows. Normalement, c’est 0L pour les messages windows, 1L ( **TRUE**) pour les messages de commande.  
  
### <a name="remarks"></a>Notes  
 N’appelez pas directement cette fonction membre.  
  
 L’implémentation par défaut de cette fonction membre crée une boîte de message. Si l’exception non interceptée provient d’un menu, barre d’outils ou d’échec de la commande accélérateur, la boîte de message affiche un message « Échec de la commande » ; dans le cas contraire, il affiche un message « erreur d’application interne ».  
  
 Remplacez cette fonction membre pour fournir la gestion globale de vos exceptions. Appelez uniquement les fonctionnalités de base si vous voulez que la boîte de message à afficher.  
  
##  <a name="a-nameregistera--cwinappregister"></a><a name="register"></a>CWinApp::Register  
 Exécute toutes les tâches d’inscription non gérées par `RegisterShellFileTypes`.  
  
```  
virtual BOOL Register();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro en cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 L’implémentation par défaut retourne simplement TRUE. Remplacez cette fonction pour fournir toutes les étapes d’enregistrement personnalisé.  
  
##  <a name="a-nameregistershellfiletypesa--cwinappregistershellfiletypes"></a><a name="registershellfiletypes"></a>CWinApp::RegisterShellFileTypes  
 Appelez cette fonction membre pour inscrire tous les types de documents de votre application avec le Gestionnaire de fichiers Windows.  
  
```  
void RegisterShellFileTypes(BOOL bCompat = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bCompat`  
 `TRUE`Ajoute des entrées d’inscription pour les commandes shell d’impression et imprimer vers, permettant à un utilisateur d’imprimer des fichiers directement à partir de l’interpréteur de commandes ou en faisant glisser le fichier vers un objet printer. Il ajoute également une clé DefaultIcon. Par défaut, ce paramètre est `FALSE` pour la compatibilité descendante.  
  
### <a name="remarks"></a>Notes  
 Cela permet à l’utilisateur d’ouvrir un fichier de données créé par votre application en double-cliquant dessus dans Gestionnaire de fichiers. Appelez `RegisterShellFileTypes` après avoir appelé [AddDocTemplate](#adddoctemplate) pour chacun des modèles de document dans votre application. Également appeler le [EnableShellOpen](#enableshellopen) fonction membre lorsque vous appelez `RegisterShellFileTypes`.  
  
 `RegisterShellFileTypes`effectue une itération dans la liste des [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) objets que l’application gère et, pour chaque modèle de document, ajoute des entrées à la base de données d’inscription gérée par Windows pour les associations de fichiers. Le Gestionnaire de fichiers utilise ces entrées pour ouvrir un fichier de données lorsque l’utilisateur double-clique dessus. Ceci élimine la nécessité d’envoyer un. Fichier REG avec votre application.  
  
> [!NOTE]
> `RegisterShellFileTypes`fonctionne uniquement si l’utilisateur exécute le programme avec des droits d’administrateur. Si le programme n’a pas de droits d’administrateur, il ne peut pas modifier les clés de Registre.  
  
 Si la base de registres associe déjà une extension de nom de fichier donné à un autre type de fichier, aucune nouvelle association n’est créée. Consultez la `CDocTemplate` classe pour le format de chaînes nécessaires pour enregistrer ces informations.  
  
##  <a name="a-nameregisterwithrestartmanagera--cwinappregisterwithrestartmanager"></a><a name="registerwithrestartmanager"></a>CWinApp::RegisterWithRestartManager  
 Enregistre l’application avec le Gestionnaire de redémarrage.  
  
```  
virtual HRESULT RegisterWithRestartManager(
BOOL bRegisterRecoveryCallback,  
const CString& strRestartIdentifier);

 
virtual HRESULT RegisterWithRestartManager(
LPCWSTR pwzCommandLineArgs,  
DWORD dwRestartFlags,  
APPLICATION_RECOVERY_CALLBACK pRecoveryCallback,  
LPVOID lpvParam,  
DWORD dwPingInterval,  
DWORD dwCallbackFlags);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|[in] `bRegisterRecoveryCallback`|`TRUE`Indique que cette instance de l’application utilise une fonction de rappel de récupération ; `FALSE` indique qu’il n’existe pas. L’infrastructure appelle la fonction de rappel de récupération lorsque l’application se ferme de façon inattendue. Pour plus d’informations, consultez [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).|  
|[in] `strRestartIdentifier`|Chaîne unique qui identifie cette instance du Gestionnaire de redémarrage. L’identificateur de gestionnaire de redémarrage est unique pour chaque instance d’une application.|  
|[in] `pwzCommandLineArgs`|Chaîne qui contient les arguments supplémentaires à partir de la ligne de commande.|  
|[in] `dwRestartFlags`|Indicateurs facultatifs pour le Gestionnaire de redémarrage. Pour plus d'informations, consultez la section Remarques.|  
|[in] `pRecoveryCallback`|La fonction de rappel de récupération. Cette fonction doit prendre un `LPVOID` paramètre comme entrée et retournent un `DWORD`. La fonction de rappel de récupération par défaut est `CWinApp::ApplicationRecoveryCallback`.|  
|[in] `lpvParam`|Le paramètre d’entrée pour la fonction de rappel de récupération. Pour plus d’informations, consultez [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).|  
|[in] `dwPingInterval`|La longueur de la durée d’attente par le Gestionnaire de redémarrage pour la fonction de rappel de récupération retourner. Ce paramètre est exprimée en millisecondes.|  
|[in] `dwCallbackFlags`|Indicateurs transmis à la fonction de rappel de récupération. Réservé à un usage ultérieur.|  
  
### <a name="return-value"></a>Valeur de retour  
 `S_OK`Si la méthode a réussi ; Sinon, un code d’erreur.  
  
### <a name="remarks"></a>Remarques  
 Si votre application utilise l’implémentation MFC par défaut pour les fichiers d’enregistrement automatique, vous devez utiliser la version simple de `RegisterWithRestartManager`. Utilisez la version complexe de `RegisterWithRestartManager` si vous souhaitez personnaliser le comportement d’enregistrement automatique de votre application.  
  
 Si vous appelez cette méthode avec une chaîne vide pour `strRestartIdentifier`, `RegisterWithRestartManager` crée une chaîne d’identificateur unique pour cette instance du redémarrage manager.  
  
 Lorsqu’une application se ferme de façon inattendue, le Gestionnaire de redémarrage redémarre l’application à partir de la ligne de commande et fournit que l’unique redémarrer identificateur comme un argument facultatif. Dans ce scénario, le framework appelle `RegisterWithRestartManager` deux fois. Le premier appel produit de [CWinApp::InitInstance](#initinstance) avec une chaîne vide pour l’identificateur de chaîne. Ensuite, la méthode [CWinApp::ProcessShellCommand](#processshellcommand) appelle `RegisterWithRestartManager` avec l’identificateur unique de redémarrage.  
  
 Une fois que vous inscrivez une application avec le Gestionnaire de redémarrage, le Gestionnaire de redémarrage surveille l’application. Si l’application se ferme de façon inattendue, le Gestionnaire de redémarrage appelle la fonction de rappel de récupération pendant le processus de fermeture. Les attentes de gestionnaire de redémarrage la `dwPingInterval` d’une réponse de la fonction de rappel de récupération. Si la fonction de rappel de récupération ne répond pas dans ce délai, l’application se ferme sans exécuter la fonction de rappel de récupération.  
  
 Par défaut, les dwRestartFlags ne sont pas pris en charge mais sont disponibles pour une utilisation ultérieure. Les valeurs possibles pour `dwRestartFlags` sont les suivantes :  
  
- `RESTART_NO_CRASH`  
  
- `RESTART_NO_HANG`  
  
- `RESTART_NO_PATCH`  
  
- `RESTART_NO_REBOOT`  
  
##  <a name="a-namereopenpreviousfilesatrestarta--cwinappreopenpreviousfilesatrestart"></a><a name="reopenpreviousfilesatrestart"></a>CWinApp::ReopenPreviousFilesAtRestart  
 Détermine si le Gestionnaire de redémarrage s’ouvre à nouveau les fichiers ont lors de l’application s’est terminé de façon inattendue.  
  
```  
virtual BOOL ReopenPreviousFilesAtRestart() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Indique la rouvre le Gestionnaire de redémarrage les fichiers précédemment ouverts ; `FALSE` indique le Gestionnaire de redémarrage ne le fait pas.  
  
##  <a name="a-namerestartinstancea--cwinapprestartinstance"></a><a name="restartinstance"></a>CWinApp::RestartInstance  
 Gère le redémarrage d’une application lancé par le Gestionnaire de redémarrage.  
  
```  
virtual BOOL CWinApp::RestartInstance();
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le Gestionnaire de récupération de données s’ouvre précédemment documents ouverts. `FALSE` si le Gestionnaire de récupération de données comporte une erreur ou si aucun document ouvert précédemment.  
  
### <a name="remarks"></a>Remarques  
 Lorsque le Gestionnaire de redémarrage redémarre une application, l’infrastructure appelle cette méthode. Cette méthode récupère le Gestionnaire de récupération de données et restaure les fichiers enregistrée automatiquement. Cette méthode appelle [CDataRecoveryHandler::RestoreAutosavedDocuments](../../mfc/reference/cdatarecoveryhandler-class.md#restoreautosaveddocuments) pour déterminer si l’utilisateur souhaite restaurer les fichiers enregistrée automatiquement.  
  
 Cette méthode retourne `FALSE` si le [CDataRecoveryHandler](../../mfc/reference/cdatarecoveryhandler-class.md) détermine qu’il n’y a aucun document ouvert. S’il n’y a aucun document ouvert, l’application démarre normalement.  
  
##  <a name="a-namerestoreautosavedfilesatrestarta--cwinapprestoreautosavedfilesatrestart"></a><a name="restoreautosavedfilesatrestart"></a>CWinApp::RestoreAutosavedFilesAtRestart  
 Détermine si le Gestionnaire de redémarrage restaure les fichiers enregistrée automatiquement lorsqu’elle redémarre l’application.  
  
```  
virtual BOOL RestoreAutosavedFilesAtRestart() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Indique les fichiers enregistrée automatiquement des restaurations du Gestionnaire de redémarrage ; `FALSE` indique le Gestionnaire de redémarrage ne le fait pas.  
  
##  <a name="a-nameruna--cwinapprun"></a><a name="run"></a>CWinApp::Run  
 Fournit une boucle de message par défaut.  
  
```  
virtual int Run();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un `int` valeur retournée par `WinMain`.  
  
### <a name="remarks"></a>Remarques  
 **Exécutez** acquiert et distribue des messages de Windows jusqu'à ce que l’application reçoit une **WM_QUIT** message. Si la file d’attente de messages de l’application ne contient actuellement aucun message, **exécuter** appelle [OnIdle](#onidle) pour exécuter le traitement des temps d’inactivité. Messages entrants sont transmis à la [PreTranslateMessage](#pretranslatemessage) fonction membre pour un traitement spécial, puis à la fonction **TranslateMessage** pour la traduction de clavier standard ; Enfin, le **DispatchMessage** Windows fonction est appelée.  
  
 **Exécutez** est rarement substituée, mais vous pouvez remplacer pour fournir un comportement spécial.  
  
##  <a name="a-namerunautomateda--cwinapprunautomated"></a><a name="runautomated"></a>CWinApp::RunAutomated  
 Appelez cette fonction pour déterminer si le « **/Automation**« ou » **-Automation**» option est présente, ce qui indique si l’application serveur a été lancée par une application cliente.  
  
```  
BOOL RunAutomated();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’option a été trouvée ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Le cas échéant, l’option est supprimée à partir de la ligne de commande. Pour plus d’informations sur OLE Automation, consultez l’article [serveurs Automation](../../mfc/automation-servers.md).  
  
##  <a name="a-namerunembeddeda--cwinapprunembedded"></a><a name="runembedded"></a>CWinApp::RunEmbedded  
 Appelez cette fonction pour déterminer si le « **/Embedding**« ou » **-Embedding**» option est présente, ce qui indique si l’application serveur a été lancée par une application cliente.  
  
```  
BOOL RunEmbedded();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’option a été trouvée ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Le cas échéant, l’option est supprimée à partir de la ligne de commande. Pour plus d’informations sur l’incorporation, consultez l’article [serveurs : implémentation d’un serveur](../../mfc/servers-implementing-a-server.md).  
  
##  <a name="a-namesaveallmodifieda--cwinappsaveallmodified"></a><a name="saveallmodified"></a>CWinApp::SaveAllModified  
 Appelée par l’infrastructure pour enregistrer tous les documents lors de la fenêtre frame principale de l’application doit être fermée, ou via un `WM_QUERYENDSESSION` message.  
  
```  
virtual BOOL SaveAllModified();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si elle est sécurisée arrêter l’application ; 0 s’il est risqué d’arrêter l’application.  
  
### <a name="remarks"></a>Notes  
 L’implémentation par défaut de cette fonction membre appelle le [CDocument::SaveModified](../../mfc/reference/cdocument-class.md#savemodified) fonction membre pour tous les documents modifiés dans l’application.  
  
##  <a name="a-nameselectprintera--cwinappselectprinter"></a><a name="selectprinter"></a>CWinApp::SelectPrinter  
 Appelez cette fonction membre pour sélectionner une imprimante spécifique et libérer l’imprimante qui a été précédemment sélectionné dans la boîte de dialogue d’impression.  
  
```  
void SelectPrinter(
    HANDLE hDevNames,  
    HANDLE hDevMode,  
    BOOL bFreeOld = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `hDevNames`  
 Un handle vers un [DEVNAMES](../../mfc/reference/devnames-structure.md) structure qui identifie les pilotes, les périphériques et les noms de ports de sortie d’une imprimante spécifique.  
  
 `hDevMode`  
 Un handle vers un [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) structure qui spécifie des informations sur l’environnement d’une imprimante et de l’initialisation du périphérique.  
  
 *bFreeOld*  
 Libère l’imprimante sélectionnée précédemment.  
  
### <a name="remarks"></a>Remarques  
 Si les deux `hDevMode` et `hDevNames` sont **NULL**, `SelectPrinter` utilise l’imprimante par défaut.  
  
##  <a name="a-namesethelpmodea--cwinappsethelpmode"></a><a name="sethelpmode"></a>CWinApp::SetHelpMode  
 Définit le type d’aide de l’application.  
  
```  
void SetHelpMode(AFX_HELP_TYPE eHelpType);
```  
  
### <a name="parameters"></a>Paramètres  
 `eHelpType`  
 Spécifie le type d’aide à utiliser. Consultez la page [CWinApp::m_eHelpType](#m_ehelptype) pour plus d’informations.  
  
### <a name="remarks"></a>Remarques  
 Définit le type d’aide de l’application.  
  
 Pour définir le type d’aide de votre application à HTMLHelp, vous pouvez appeler [EnableHTMLHelp](#enablehtmlhelp). Une fois que vous appelez `EnableHTMLHelp`, votre application doit utiliser HTMLHelp que son application d’aide. Si vous souhaitez modifier pour utiliser WinHelp, vous pouvez appeler `SetHelpMode` et `eHelpType` à **afxWinHelp**.  
  
##  <a name="a-namesetregistrykeya--cwinappsetregistrykey"></a><a name="setregistrykey"></a>CWinApp::SetRegistryKey  
 Provoque des paramètres d’application sont stockées dans le Registre au lieu des fichiers INI.  
  
```  
void SetRegistryKey(LPCTSTR lpszRegistryKey);  
void SetRegistryKey(UINT nIDRegistryKey);
```  
  
### <a name="parameters"></a>Paramètres  
 *lpszRegistryKey*  
 Pointeur vers une chaîne contenant le nom de la clé.  
  
 *nIDRegistryKey*  
 ID d’une ressource de chaîne contenant le nom de la clé de Registre.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction définit *m_pszRegistryKey*, qui est ensuite utilisé par le `GetProfileInt`, `GetProfileString`, `WriteProfileInt`, et `WriteProfileString` les fonctions membres de `CWinApp`. Si cette fonction a été appelée, la liste de fichiers plus récemment utilisés (MRU) est également stockée dans le Registre. La clé de Registre est généralement le nom de la société. Il est stocké dans une clé sous la forme suivante : HKEY_CURRENT_USER\Software\\<company></company>\>\\<application></application>\>\\<section></section>\>\\<value></value>\>.  
  
##  <a name="a-namesupportsapplicationrecoverya--cwinappsupportsapplicationrecovery"></a><a name="supportsapplicationrecovery"></a>CWinApp::SupportsApplicationRecovery  
 Détermine si le Gestionnaire de redémarrage permet de récupérer une application qui s’est terminé de façon inattendue.  
  
```  
virtual BOOL SupportsApplicationRecovery() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Indique la restaure Gestionnaire de redémarrage de l’application ; `FALSE` indique le Gestionnaire de redémarrage ne le fait pas.  
  
##  <a name="a-namesupportsautosaveatintervala--cwinappsupportsautosaveatinterval"></a><a name="supportsautosaveatinterval"></a>CWinApp::SupportsAutosaveAtInterval  
 Détermine si le Gestionnaire de redémarrage enregistre automatiquement ouvre des documents à intervalles réguliers.  
  
```  
virtual BOOL SupportsAutosaveAtInterval() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Indique le Gestionnaire de redémarrage enregistre automatiquement documents ouverts. `FALSE` indique le Gestionnaire de redémarrage ne le fait pas.  
  
##  <a name="a-namesupportsautosaveatrestarta--cwinappsupportsautosaveatrestart"></a><a name="supportsautosaveatrestart"></a>CWinApp::SupportsAutosaveAtRestart  
 Détermine si le Gestionnaire de redémarrage enregistre automatiquement les documents ouverts lorsque l’application redémarre.  
  
```  
virtual BOOL SupportsAutosaveAtRestart() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Indique le Gestionnaire de redémarrage enregistre automatiquement les documents ouverts lorsque l’application redémarre ; `FALSE` indique le Gestionnaire de redémarrage ne le fait pas.  
  
##  <a name="a-namesupportsrestartmanagera--cwinappsupportsrestartmanager"></a><a name="supportsrestartmanager"></a>CWinApp::SupportsRestartManager  
 Détermine si l’application prend en charge le Gestionnaire de redémarrage.  
  
```  
virtual BOOL SupportsRestartManager() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Indique l’application prend en charge le Gestionnaire de redémarrage ; `FALSE` indique n’est pas le cas de l’application.  
  
##  <a name="a-nameunregistera--cwinappunregister"></a><a name="unregister"></a>CWinApp::Unregister  
 Annule l’inscription de tous les fichiers enregistrés par l’objet application.  
  
```  
virtual BOOL Unregister();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro en cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Le `Unregister` fonction annule l’inscription effectuée par l’objet application et la [enregistrer](#register) (fonction). Normalement, les deux fonctions sont appelées implicitement par MFC et n’apparaissent donc pas dans votre code.  
  
 Remplacez cette fonction pour effectuer les étapes d’annulation d’inscription personnalisée.  
  
##  <a name="a-nameunregistershellfiletypesa--cwinappunregistershellfiletypes"></a><a name="unregistershellfiletypes"></a>CWinApp::UnregisterShellFileTypes  
 Appelez cette fonction membre pour annuler l’inscription de tous les types de documents de votre application avec le Gestionnaire de fichiers Windows.  
  
```  
void UnregisterShellFileTypes();
```  
  
##  <a name="a-namewinhelpa--cwinappwinhelp"></a><a name="winhelp"></a>CWinApp::WinHelp  
 Appelez cette fonction membre pour appeler l’application WinHelp.  
  
```  
virtual void WinHelp(
    DWORD_PTR dwData,  
    UINT nCmd = HELP_CONTEXT);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwData`  
 Spécifie les données supplémentaires. La valeur utilisée dépend de la valeur de le `nCmd` paramètre.  
  
 `nCmd`  
 Spécifie le type d’aide demandée. Pour obtenir la liste des valeurs possibles et comment elles affectent le `dwData` paramètre, consultez le [WinHelp](http://msdn.microsoft.com/library/windows/desktop/bb762267) fonction Windows.  
  
### <a name="remarks"></a>Remarques  
 Le framework appelle également cette fonction pour appeler l’application WinHelp.  
  
 Le framework ferme automatiquement l’application WinHelp lorsque votre application s’arrête.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#53;](../../mfc/reference/codesnippet/cpp/cwinapp-class_28.cpp)]  
  
##  <a name="a-namewriteprofilebinarya--cwinappwriteprofilebinary"></a><a name="writeprofilebinary"></a>CWinApp::WriteProfileBinary  
 Appelez cette fonction membre pour écrire des données binaires dans la section du Registre de l’application spécifiée ou. Fichier INI.  
  
```  
BOOL WriteProfileBinary(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    LPBYTE pData,  
    UINT nBytes);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszSection`  
 Pointe vers une chaîne terminée par le caractère null qui spécifie la section contenant l’entrée. Si la section n’existe pas, il est créé. Le nom de la section est cas indépendantes ; la chaîne peut être toute combinaison de lettres majuscules et les minuscules.  
  
 `lpszEntry`  
 Pointe vers une chaîne terminée par le caractère null qui contient l’entrée à laquelle la valeur doit être écrite. Si l’entrée n’existe pas dans la section spécifiée, il est créé.  
  
 `pData`  
 Pointe vers les données doivent être écrites.  
  
 `nBytes`  
 Contient le nombre d’octets à écrire.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="example"></a>Exemple  
 Cet exemple utilise `CWinApp* pApp = AfxGetApp();` pour obtenir la classe CWinApp illustrant une manière qui `WriteProfileBinary` et `GetProfileBinary` peut être utilisée à partir de n’importe quelle fonction dans une application MFC.  
  
 [!code-cpp[NVC_MFCWindowing&#54;](../../mfc/reference/codesnippet/cpp/cwinapp-class_29.cpp)]  
  
 Pour un autre exemple, consultez l’exemple de [CWinApp::GetProfileBinary](#getprofilebinary).  
  
##  <a name="a-namewriteprofileinta--cwinappwriteprofileint"></a><a name="writeprofileint"></a>CWinApp::WriteProfileInt  
 Appelez cette fonction membre pour écrire la valeur spécifiée dans la section du Registre de l’application spécifiée ou. Fichier INI.  
  
```  
BOOL WriteProfileInt(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    int nValue);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszSection`  
 Pointe vers une chaîne terminée par le caractère null qui spécifie la section contenant l’entrée. Si la section n’existe pas, il est créé. Le nom de la section est cas indépendantes ; la chaîne peut être toute combinaison de lettres majuscules et les minuscules.  
  
 `lpszEntry`  
 Pointe vers une chaîne terminée par le caractère null qui contient l’entrée à laquelle la valeur doit être écrite. Si l’entrée n’existe pas dans la section spécifiée, il est créé.  
  
 `nValue`  
 Contient la valeur à écrire.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="example"></a>Exemple  
 Cet exemple utilise `CWinApp* pApp = AfxGetApp();` pour obtenir la classe CWinApp illustrant une manière qui `WriteProfileString`, `WriteProfileInt`, `GetProfileString`, et `GetProfileInt` peut être utilisée à partir de n’importe quelle fonction dans une application MFC.  
  
 [!code-cpp[NVC_MFCWindowing&#43;](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]  
  
 Pour un autre exemple, consultez l’exemple de [CWinApp::GetProfileInt](#getprofileint).  
  
##  <a name="a-namewriteprofilestringa--cwinappwriteprofilestring"></a><a name="writeprofilestring"></a>CWinApp::WriteProfileString  
 Appelez cette fonction membre pour écrire la chaîne spécifiée dans la section du Registre de l’application spécifiée ou. Fichier INI.  
  
```  
BOOL WriteProfileString(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    LPCTSTR lpszValue);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszSection`  
 Pointe vers une chaîne terminée par le caractère null qui spécifie la section contenant l’entrée. Si la section n’existe pas, il est créé. Le nom de la section est cas indépendantes ; la chaîne peut être toute combinaison de lettres majuscules et les minuscules.  
  
 `lpszEntry`  
 Pointe vers une chaîne terminée par le caractère null qui contient l’entrée à laquelle la valeur doit être écrite. Si l’entrée n’existe pas dans la section spécifiée, il est créé. Si ce paramètre est `NULL`, la section spécifiée par `lpszSection` est supprimé.  
  
 `lpszValue`  
 Pointe vers la chaîne à écrire. Si ce paramètre est `NULL`, l’entrée spécifiée par le `lpszEntry` paramètre est supprimé.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#43;](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]  
  
 Pour un autre exemple, consultez l’exemple de [CWinApp::GetProfileInt](#getprofileint).  
  
##  <a name="a-namesetappida--cwinappsetappid"></a><a name="setappid"></a>CWinApp::SetAppID  
 ID de modèle d’Application utilisateur définit de manière explicite pour l’application. Cette méthode doit être appelée avant que n’importe quelle interface utilisateur s’affiche à l’utilisateur (le meilleur emplacement est le constructeur d’application).  
  
```  
void SetAppID(LPCTSTR lpcszAppID);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpcszAppID`  
 Spécifie l’ID de modèle d’Application utilisateur.  
  
### <a name="remarks"></a>Remarques  
  
## <a name="see-also"></a>Voir aussi  
 [CWinThread (classe)](../../mfc/reference/cwinthread-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Comment : ajouter la prise en charge du Gestionnaire de redémarrage](../../mfc/how-to-add-restart-manager-support.md)




