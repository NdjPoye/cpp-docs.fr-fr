---
title: "CWinApp Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CWinApp"
  - "hInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "application objects [C++]"
  - "CWinApp class"
  - "HINSTANCE"
  - "main object"
ms.assetid: e426a3cd-0d15-40d6-bd55-beaa5feb2343
caps.latest.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 29
---
# CWinApp Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe de base dont vous dérivez un objet application Windows.  
  
## Syntaxe  
  
```  
class CWinApp : public CWinThread  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CWinApp::CWinApp](../Topic/CWinApp::CWinApp.md)|Construit un objet `CWinApp`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CWinApp::AddDocTemplate](../Topic/CWinApp::AddDocTemplate.md)|Ajoute un modèle de document à la liste de modèles de document disponibles.|  
|[CWinApp::AddToRecentFileList](../Topic/CWinApp::AddToRecentFileList.md)|Ajoute un nom de fichier à la liste des derniers fichiers utilisés de \(MRU\).|  
|[CWinApp::ApplicationRecoveryCallback](../Topic/CWinApp::ApplicationRecoveryCallback.md)|Appelé par l'infrastructure lorsque l'application s'arrête de façon inattendue.|  
|[CWinApp::CloseAllDocuments](../Topic/CWinApp::CloseAllDocuments.md)|Ferme tous les documents ouverts.|  
|[CWinApp::CreatePrinterDC](../Topic/CWinApp::CreatePrinterDC.md)|Crée un contexte de périphérique d'impression.|  
|[CWinApp::DelRegTree](../Topic/CWinApp::DelRegTree.md)|Supprime une clé spécifiée et toutes ses sous\-clés.|  
|[CWinApp::DoMessageBox](../Topic/CWinApp::DoMessageBox.md)|Implémente [AfxMessageBox](../Topic/AfxMessageBox.md) pour l'application.|  
|[CWinApp::DoWaitCursor](../Topic/CWinApp::DoWaitCursor.md)|Active ou désactive le curseur d'attente de démarrer et d'arrêt.|  
|[CWinApp::EnableD2DSupport](../Topic/CWinApp::EnableD2DSupport.md)|Active la prise en charge d' `D2D` d'application.  Appelez cette méthode avant l'initialisation de la fenêtre principale.|  
|[CWinApp::EnableHtmlHelp](../Topic/CWinApp::EnableHtmlHelp.md)|Implémente HTMLHelp pour l'application, plutôt que WinHelp.|  
|[CWinApp::EnableTaskbarInteraction](../Topic/CWinApp::EnableTaskbarInteraction.md)|Active l'interaction de barre des tâches.|  
|[CWinApp::ExitInstance](../Topic/CWinApp::ExitInstance.md)|Substitution à nettoyer lorsque votre application se termine.|  
|[CWinApp::GetApplicationRecoveryParameter](../Topic/CWinApp::GetApplicationRecoveryParameter.md)|Récupère le paramètre d'entrée pour la méthode de redémarrage de l'application.|  
|[CWinApp::GetApplicationRecoveryPingInterval](../Topic/CWinApp::GetApplicationRecoveryPingInterval.md)|Retourne la durée que le gestionnaire de redémarrage attend la fonction de rappel de redémarrage pour retourner.|  
|[CWinApp::GetApplicationRestartFlags](../Topic/CWinApp::GetApplicationRestartFlags.md)|Retourne les balises pour le gestionnaire de redémarrage.|  
|[CWinApp::GetAppRegistryKey](../Topic/CWinApp::GetAppRegistryKey.md)|Clé de retour pour HKEY\_CURRENT\_USER \\"Software"\\RegistryKey\\ProfileName.|  
|[CWinApp::GetDataRecoveryHandler](../Topic/CWinApp::GetDataRecoveryHandler.md)|Obtient le gestionnaire de récupération de données pour cette instance de l'application.|  
|[CWinApp::GetFirstDocTemplatePosition](../Topic/CWinApp::GetFirstDocTemplatePosition.md)|Extrait la position du premier modèle de document.|  
|[CWinApp::GetHelpMode](../Topic/CWinApp::GetHelpMode.md)|Récupère le type d'aide utilisé par l'application.|  
|[CWinApp::GetNextDocTemplate](../Topic/CWinApp::GetNextDocTemplate.md)|Extrait la position d'un modèle de document.  Peut être utilisé de manière récursive.|  
|[CWinApp::GetPrinterDeviceDefaults](../Topic/CWinApp::GetPrinterDeviceDefaults.md)|Récupère les valeurs par défaut de périphérique d'impression.|  
|[CWinApp::GetProfileBinary](../Topic/CWinApp::GetProfileBinary.md)|Récupère des données binaires d'une entrée dans le fichier .ini de l'application.|  
|[CWinApp::GetProfileInt](../Topic/CWinApp::GetProfileInt.md)|Récupère un entier d'une entrée dans le fichier .ini de l'application.|  
|[CWinApp::GetProfileString](../Topic/CWinApp::GetProfileString.md)|Extrait une chaîne d'entrée dans le fichier .ini de l'application.|  
|[CWinApp::GetSectionKey](../Topic/CWinApp::GetSectionKey.md)|Clé de retour pour HKEY\_CURRENT\_USER \\"Software"\\RegistryKey\\AppName\\lpszSection.|  
|[CWinApp::HideApplication](../Topic/CWinApp::HideApplication.md)|Masque l'application avant de fermer tous les documents.|  
|[CWinApp::HtmlHelp](../Topic/CWinApp::HtmlHelp.md)|Appelle la fonction Windows d' `HTMLHelp` .|  
|[CWinApp::InitInstance](../Topic/CWinApp::InitInstance.md)|La substitution pour effectuer des fenêtres instance de l'initialisation, telle que la création de vos objets window.|  
|[CWinApp::IsTaskbarInteractionEnabled](../Topic/CWinApp::IsTaskbarInteractionEnabled.md)|Indique si l'interaction de barre des tâches Windows 7 est activée.|  
|[CWinApp::LoadCursor](../Topic/CWinApp::LoadCursor.md)|Charge une ressource curseur.|  
|[CWinApp::LoadIcon](../Topic/CWinApp::LoadIcon.md)|Charge une ressource icône.|  
|[CWinApp::LoadOEMCursor](../Topic/CWinApp::LoadOEMCursor.md)|Charge un curseur intégré OEM par windows que les constantes d' **OCR\_** spécifiez dans WINDOWS.H.|  
|[CWinApp::LoadOEMIcon](../Topic/CWinApp::LoadOEMIcon.md)|Charge une icône prédéfinie OEM par windows que les constantes d' **OIC\_** spécifiez dans WINDOWS.H.|  
|[CWinApp::LoadStandardCursor](../Topic/CWinApp::LoadStandardCursor.md)|Charge un curseur prédéfini par windows que les constantes d' **IDC\_** spécifiez dans WINDOWS.H.|  
|[CWinApp::LoadStandardIcon](../Topic/CWinApp::LoadStandardIcon.md)|Charge une icône intégrée par windows que les constantes d' **IDI\_** spécifiez dans WINDOWS.H.|  
|[CWinApp::OnDDECommand](../Topic/CWinApp::OnDDECommand.md)|Appelé par l'infrastructure en réponse à un échange dynamique de données \(DDE\) exécutez la commande.|  
|[CWinApp::OnIdle](../Topic/CWinApp::OnIdle.md)|Substitution pour exécuter pendant le traitement des temps d'inactivité spécifique à l'application.|  
|[CWinApp::OpenDocumentFile](../Topic/CWinApp::OpenDocumentFile.md)|Appelé par l'infrastructure pour ouvrir un document à partir d'un fichier.|  
|[CWinApp::ParseCommandLine](../Topic/CWinApp::ParseCommandLine.md)|Analyse des paramètres et balises dans la ligne de commande.|  
|[CWinApp::PreTranslateMessage](../Topic/CWinApp::PreTranslateMessage.md)|Messages de filtres pour qu'ils soient distribués aux fonctions Windows [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) et [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934).|  
|[CWinApp::ProcessMessageFilter](../Topic/CWinApp::ProcessMessageFilter.md)|Certains messages intercepte d'avant qu'ils atteignent l'application.|  
|[CWinApp::ProcessShellCommand](../Topic/CWinApp::ProcessShellCommand.md)|Gère les arguments de ligne de commande et des balises.|  
|[CWinApp::ProcessWndProcException](../Topic/CWinApp::ProcessWndProcException.md)|Intercepte toutes les exceptions non gérées levées par le message et des gestionnaires de commandes de l'application.|  
|[CWinApp::Register](../Topic/CWinApp::Register.md)|Performs avez personnalisé l'inscription.|  
|[CWinApp::RegisterWithRestartManager](../Topic/CWinApp::RegisterWithRestartManager.md)|Stocke l'application avec le gestionnaire de redémarrage.|  
|[CWinApp::ReopenPreviousFilesAtRestart](../Topic/CWinApp::ReopenPreviousFilesAtRestart.md)|Détermine si le gestionnaire de redémarrage rouvre les fichiers qui étaient ouverts lorsque l'application a quitté de façon inattendue.|  
|[CWinApp::RestartInstance](../Topic/CWinApp::RestartInstance.md)|Gère le redémarrage d'application initialisée par le gestionnaire de redémarrage.|  
|[CWinApp::RestoreAutosavedFilesAtRestart](../Topic/CWinApp::RestoreAutosavedFilesAtRestart.md)|Détermine si le gestionnaire de redémarrage restaure les fichiers sauvegardés automatiquement lorsqu'il redémarre l'application.|  
|[CWinApp::Run](../Topic/CWinApp::Run.md)|Exécute la boucle de message par défaut.  Substitution pour personnaliser la boucle de message.|  
|[CWinApp::RunAutomated](../Topic/CWinApp::RunAutomated.md)|Teste la ligne de commande de l'application pour l'option d' **\/Automation** .  Obsolète.  À la place, utilisez la valeur dans [CCommandLineInfo::m\_bRunAutomated](../Topic/CCommandLineInfo::m_bRunAutomated.md) après avoir appelé [ParseCommandLine](../Topic/CWinApp::ParseCommandLine.md).|  
|[CWinApp::RunEmbedded](../Topic/CWinApp::RunEmbedded.md)|Teste la ligne de commande de l'application pour l'option d' **\/Embedding** .  Obsolète.  À la place, utilisez la valeur dans [CCommandLineInfo::m\_bRunEmbedded](../Topic/CCommandLineInfo::m_bRunEmbedded.md) après avoir appelé [ParseCommandLine](../Topic/CWinApp::ParseCommandLine.md).|  
|[CWinApp::SaveAllModified](../Topic/CWinApp::SaveAllModified.md)|Invite l'utilisateur à enregistrer tous les documents modifiés.|  
|[CWinApp::SelectPrinter](../Topic/CWinApp::SelectPrinter.md)|Sélectionne une imprimante précédemment indiquée par un utilisateur dans une boîte de dialogue d'impression.|  
|[CWinApp::SetHelpMode](../Topic/CWinApp::SetHelpMode.md)|Les jeux et initialise le type d'aide utilisé par l'application.|  
|[CWinApp::SupportsApplicationRecovery](../Topic/CWinApp::SupportsApplicationRecovery.md)|Détermine si le gestionnaire de redémarrage est récupérée une application qui a quitté de façon inattendue.|  
|[CWinApp::SupportsAutosaveAtInterval](../Topic/CWinApp::SupportsAutosaveAtInterval.md)|Détermine si le gestionnaire de redémarrage enregistre les documents ouverts automatiquement à intervalle régulier.|  
|[CWinApp::SupportsAutosaveAtRestart](../Topic/CWinApp::SupportsAutosaveAtRestart.md)|Détermine si le gestionnaire de redémarrage enregistre les documents ouverts lorsque l'application redémarre.|  
|[CWinApp::SupportsRestartManager](../Topic/CWinApp::SupportsRestartManager.md)|Détermine si l'application prend en charge le gestionnaire de redémarrage.|  
|[CWinApp::Unregister](../Topic/CWinApp::Unregister.md)|Annule l'inscription tout connu pour être enregistré par l'objet d' `CWinApp` .|  
|[CWinApp::WinHelp](../Topic/CWinApp::WinHelp.md)|Appelle la fonction Windows d' `WinHelp` .|  
|[CWinApp::WriteProfileBinary](../Topic/CWinApp::WriteProfileBinary.md)|Écrit des données binaires à une entrée dans le fichier.ini de l'application.|  
|[CWinApp::WriteProfileInt](../Topic/CWinApp::WriteProfileInt.md)|Écrit un entier à une entrée dans le fichier.ini de l'application.|  
|[CWinApp::WriteProfileString](../Topic/CWinApp::WriteProfileString.md)|Écrit une chaîne dans une entrée dans le fichier .ini de l'application.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CWinApp::EnableShellOpen](../Topic/CWinApp::EnableShellOpen.md)|Permet à l'utilisateur des fichiers de données ouverts du gestionnaire de fichiers windows.|  
|[CWinApp::LoadStdProfileSettings](../Topic/CWinApp::LoadStdProfileSettings.md)|Charge les paramètres standard de fichier .ini et active la fonctionnalité liste des fichiers récents.|  
|[CWinApp::OnContextHelp](../Topic/CWinApp::OnContextHelp.md)|Utilisation de handles SHIFT\+F1 dans l'application.|  
|[CWinApp::OnFileNew](../Topic/CWinApp::OnFileNew.md)|Implémente la commande d' `ID_FILE_NEW` .|  
|[CWinApp::OnFileOpen](../Topic/CWinApp::OnFileOpen.md)|Implémente la commande d' `ID_FILE_OPEN` .|  
|[CWinApp::OnFilePrintSetup](../Topic/CWinApp::OnFilePrintSetup.md)|Implémente la commande d' `ID_FILE_PRINT_SETUP` .|  
|[CWinApp::OnHelp](../Topic/CWinApp::OnHelp.md)|Aide F1 de handles dans l'application \(en utilisant le contexte actuel\).|  
|[CWinApp::OnHelpFinder](../Topic/CWinApp::OnHelpFinder.md)|Gère les commandes d' `ID_HELP_FINDER` et d' `ID_DEFAULT_HELP` .|  
|[CWinApp::OnHelpIndex](../Topic/CWinApp::OnHelpIndex.md)|Gère la commande d' `ID_HELP_INDEX` et fournit une rubrique d'aide par défaut.|  
|[CWinApp::OnHelpUsing](../Topic/CWinApp::OnHelpUsing.md)|Gère la commande `ID_HELP_USING`.|  
|[CWinApp::RegisterShellFileTypes](../Topic/CWinApp::RegisterShellFileTypes.md)|Stocke les types de document de toute application avec le gestionnaire de fichiers windows.|  
|[CWinApp::SetAppID](../Topic/CWinApp::SetAppID.md)|Définit explicitement l'ID de modèle utilisateur de l'application pour l'application.  Cette méthode doit être appelée avant que toute interface utilisateur est présentée à l'utilisateur \(le meilleur emplacement est le constructeur d'application\).|  
|[CWinApp::SetRegistryKey](../Topic/CWinApp::SetRegistryKey.md)|Cause des paramètres d'application soit stocké dans le Registre au lieu des fichiers de .INI.|  
|[CWinApp::UnregisterShellFileTypes](../Topic/CWinApp::UnregisterShellFileTypes.md)|Annule l'inscription des types de document de toute application avec le gestionnaire de fichiers windows.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CWinApp::m\_bHelpMode](../Topic/CWinApp::m_bHelpMode.md)|Indique si l'utilisateur est en mode de contexte d'aide \(généralement appelé avec SHIFT\+F1\).|  
|[CWinApp::m\_eHelpType](../Topic/CWinApp::m_eHelpType.md)|Spécifie le type d'aide utilisé par l'application.|  
|[CWinApp::m\_hInstance](../Topic/CWinApp::m_hInstance.md)|Identifie l'instance actuelle de l'application.|  
|[CWinApp::m\_lpCmdLine](../Topic/CWinApp::m_lpCmdLine.md)|Pointe vers une chaîne terminée par le caractère NULL qui spécifie la ligne de commande pour l'application.|  
|[CWinApp::m\_nCmdShow](../Topic/CWinApp::m_nCmdShow.md)|Spécifie comment la fenêtre doit être affichée initialement.|  
|[CWinApp::m\_pActiveWnd](../Topic/CWinApp::m_pActiveWnd.md)|Pointeur vers la fenêtre principale de l'application conteneur lorsqu'un OLE serveur est actif sur place.|  
|[CWinApp::m\_pszAppID](../Topic/CWinApp::m_pszAppID.md)|ID de modèle utilisateur de l'application|  
|[CWinApp::m\_pszAppName](../Topic/CWinApp::m_pszAppName.md)|Spécifie le nom de l'application.|  
|[CWinApp::m\_pszExeName](../Topic/CWinApp::m_pszExeName.md)|Le nom du module de l'application.|  
|[CWinApp::m\_pszHelpFilePath](../Topic/CWinApp::m_pszHelpFilePath.md)|Le chemin d'accès au fichier d'aide de l'application.|  
|[CWinApp::m\_pszProfileName](../Topic/CWinApp::m_pszProfileName.md)|Le nom du fichier de .INI de l'application.|  
|[CWinApp::m\_pszRegistryKey](../Topic/CWinApp::m_pszRegistryKey.md)|Utilisé pour déterminer la clé de Registre complète pour stocker les paramètres de profil d'application.|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CWinApp::m\_dwRestartManagerSupportFlags](../Topic/CWinApp::m_dwRestartManagerSupportFlags.md)|Balises qui déterminent le gestionnaire de redémarrage se comporte.|  
|[CWinApp::m\_nAutosaveInterval](../Topic/CWinApp::m_nAutosaveInterval.md)|La durée en millisecondes entre sauvegarde automatiquement.|  
|[CWinApp::m\_pDataRecoveryHandler](../Topic/CWinApp::m_pDataRecoveryHandler.md)|Pointeur vers le gestionnaire de récupération de données pour l'application.|  
  
## Notes  
 Un objet d'application fournit les fonctions membres pour initialiser votre application \(et chaque instance de celle\-ci\) et pour exécuter l'application.  
  
 Chaque application qui utilise les classes MFC \(Microsoft Foundation peut uniquement contenir un objet dérivé d' `CWinApp`.  Cet objet est généré lorsque d'autres objets globaux C\+\+ sont construits et est déjà disponible lorsque les fenêtres appelle la fonction d' `WinMain` , qui est fournie par la bibliothèque MFC.  Déclarez votre objet dérivé d' `CWinApp` au niveau global.  
  
 Lorsque vous dérivez une classe d'application d' `CWinApp`, substituez la fonction membre d' [InitInstance](../Topic/CWinApp::InitInstance.md) pour créer l'objet window principal de votre application.  
  
 En plus de les fonctions membres d' `CWinApp` , la bibliothèque MFC fournit les fonctions globales suivantes pour accéder à votre objet d' `CWinApp` et d'autres informations globales :  
  
-   [AfxGetApp](../Topic/AfxGetApp.md) obtient un pointeur vers l'objet d' `CWinApp` .  
  
-   [AfxGetInstanceHandle](../Topic/AfxGetInstanceHandle.md) obtient un handle vers l'instance d'application actuelle.  
  
-   [AfxGetResourceHandle](../Topic/AfxGetResourceHandle.md) obtient un handle aux ressources de l'application.  
  
-   [AfxGetAppName](../Topic/AfxGetAppName.md) obtient un pointeur vers une chaîne contenant le nom d'application.  De même, si vous avez un pointeur vers l'objet d' `CWinApp` , utilisez `m_pszExeName` d'obtenir le nom d'application.  
  
 Consultez [CWinApp : La classe d'application](../../mfc/cwinapp-the-application-class.md) pour plus d'informations sur la classe d' `CWinApp` , notamment une vue d'ensemble des éléments suivants :  
  
-   `CWinApp`\- dérivé code écrit par l'Assistant Application.  
  
-   Le rôle d'`CWinApp` dans l'ordre d'exécution de votre application.  
  
-   Implémentations de fonction du membre par défaut d'`CWinApp`.  
  
-   Les overridables principaux d'`CWinApp`.  
  
 Le membre de **m\_hPrevInstance** n'existe plus.  Pour plus d'informations sur la détection une instance précédente de `CWinApp`, consultez l'article de la Base de connaissances « procédure identifier une instance précédente d'une application » \(KB106385\) dans [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;106385](http://support.microsoft.com/default.aspx?scid=kb;en-us;106385).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 `CWinApp`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [CWinThread Class](../../mfc/reference/cwinthread-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Comment : ajouter la prise en charge du Gestionnaire de redémarrage](../../mfc/how-to-add-restart-manager-support.md)