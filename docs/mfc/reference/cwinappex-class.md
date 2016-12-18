---
title: "CWinAppEx Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CWinAppEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinAppEx class"
ms.assetid: a3d3e053-3e22-463f-9444-c73abb1bb9d7
caps.latest.revision: 37
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWinAppEx Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CWinAppEx` gère l'état de l'application, enregistre l'état au Registre, charge l'état du Registre, initialise des gestionnaires d'application, et fournit des liens vers ces mêmes gestionnaires d'application.  
  
## Syntaxe  
  
```  
class CWinAppEx : public CWinApp  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CWinAppEx::CWinAppEx](../Topic/CWinAppEx::CWinAppEx.md)|Construit un objet `CWinAppEx`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CWinAppEx::CleanState](../Topic/CWinAppEx::CleanState.md)|Supprime les informations sur l'application du Registre Windows.|  
|[CWinAppEx::EnableLoadWindowPlacement](../Topic/CWinAppEx::EnableLoadWindowPlacement.md)|Spécifie si l'application chargera la taille et l'emplacement initiaux de la fenêtre frame principale du Registre.|  
|[CWinAppEx::EnableTearOffMenus](../Topic/CWinAppEx::EnableTearOffMenus.md)|Active des menus volants pour l'application.|  
|[CWinAppEx::EnableUserTools](../Topic/CWinAppEx::EnableUserTools.md)|Permet à l'utilisateur de créer des commandes de menu personnalisées dans l'application.|  
|[CWinAppEx::ExitInstance](../Topic/CWinAppEx::ExitInstance.md)|Appelé par l'infrastructure de la fonction membre d' `Run` pour quitter cette instance de l'application.  \(Substitutions [CWinApp::ExitInstance](../Topic/CWinApp::ExitInstance.md).\)|  
|[CWinAppEx::GetBinary](../Topic/CWinAppEx::GetBinary.md)|Lit des données binaires qui sont associées à la valeur de Registre spécifiée.|  
|[CWinAppEx::GetContextMenuManager](../Topic/CWinAppEx::GetContextMenuManager.md)|Retourne un pointeur vers l'objet global de [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) .|  
|[CWinAppEx::GetDataVersion](../Topic/CWinAppEx::GetDataVersion.md)||  
|[CWinAppEx::GetDataVersionMajor](../Topic/CWinAppEx::GetDataVersionMajor.md)|Retourne la version principale de l'application enregistrée dans le Registre Windows.|  
|[CWinAppEx::GetDataVersionMinor](../Topic/CWinAppEx::GetDataVersionMinor.md)|Retourne la version secondaire de l'application enregistrée dans le Registre Windows.|  
|[CWinAppEx::GetInt](../Topic/CWinAppEx::GetInt.md)|Lit les données numériques associées à la valeur spécifiée dans le Registre.|  
|[CWinAppEx::GetKeyboardManager](../Topic/CWinAppEx::GetKeyboardManager.md)|Retourne un pointeur vers l'objet global de [CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md) .|  
|[CWinAppEx::GetMouseManager](../Topic/CWinAppEx::GetMouseManager.md)|Retourne un pointeur vers l'objet global de [CMouseManager](../../mfc/reference/cmousemanager-class.md) .|  
|[CWinAppEx::GetObject](../Topic/CWinAppEx::GetObject.md)|Lit `CObject`\- les données dérivées associées à la valeur spécifiée dans le Registre.|  
|[CWinAppEx::GetRegSectionPath](../Topic/CWinAppEx::GetRegSectionPath.md)|Retourne une chaîne qui est le chemin d'accès d'une clé de Registre.  Ce chemin d'accès concatène le chemin d'accès relatif fourni avec le chemin d'accès d'application.|  
|[CWinAppEx::GetRegistryBase](../Topic/CWinAppEx::GetRegistryBase.md)|Retourne le chemin d'accès au Registre de l'application.|  
|[CWinAppEx::GetSectionBinary](../Topic/CWinAppEx::GetSectionBinary.md)|Lit des données binaires qui sont associées à la clé et la valeur spécifiée dans le Registre.|  
|[CWinAppEx::GetSectionInt](../Topic/CWinAppEx::GetSectionInt.md)|Données numériques lectures du Registre associé à la clé et la valeur spécifiée.|  
|[CWinAppEx::GetSectionObject](../Topic/CWinAppEx::GetSectionObject.md)|Lit les données d' `CObject` associées à la clé et la valeur spécifiée dans le Registre.|  
|[CWinAppEx::GetSectionString](../Topic/CWinAppEx::GetSectionString.md)|Lit les données de chaîne associées à la clé et la valeur spécifiée dans le Registre.|  
|[CWinAppEx::GetShellManager](../Topic/CWinAppEx::GetShellManager.md)|Retourne un pointeur vers l'objet global de [CShellManager](../../mfc/reference/cshellmanager-class.md) .|  
|[CWinAppEx::GetString](../Topic/CWinAppEx::GetString.md)|Lit les données de chaîne associées à la valeur spécifiée dans le Registre.|  
|[CWinAppEx::GetTooltipManager](../Topic/CWinAppEx::GetTooltipManager.md)|Retourne un pointeur vers l'objet global de [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) .|  
|[CWinAppEx::GetUserToolsManager](../Topic/CWinAppEx::GetUserToolsManager.md)|Retourne un pointeur vers l'objet global de [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md) .|  
|[CWinAppEx::InitContextMenuManager](../Topic/CWinAppEx::InitContextMenuManager.md)|Initialise l'objet `CContextMenuManager`.|  
|[CWinAppEx::InitKeyboardManager](../Topic/CWinAppEx::InitKeyboardManager.md)|Initialise l'objet `CKeyboardManager`.|  
|[CWinAppEx::InitMouseManager](../Topic/CWinAppEx::InitMouseManager.md)|Initialise l'objet `CMouseManager`.|  
|[CWinAppEx::InitShellManager](../Topic/CWinAppEx::InitShellManager.md)|Initialise la classe d' `CShellManager`|  
|[CWinAppEx::InitTooltipManager](../Topic/CWinAppEx::InitTooltipManager.md)|Initialise la classe `CTooltipManager`.|  
|[CWinAppEx::IsResourceSmartUpdate](../Topic/CWinAppEx::IsResourceSmartUpdate.md)||  
|[CWinAppEx::IsStateExists](../Topic/CWinAppEx::IsStateExists.md)|Indique si la clé spécifiée dans le Registre.|  
|[CWinAppEx::LoadState](../Topic/CWinAppEx::LoadState.md)|Charge l'état de l'application du Registre.|  
|[CWinAppEx::OnAppContextHelp](../Topic/CWinAppEx::OnAppContextHelp.md)|Appelé par l'infrastructure lorsque l'aide de contexte de l'utilisateur demande pour la boîte de dialogue **Personnalisation** .|  
|[CWinAppEx::OnViewDoubleClick](../Topic/CWinAppEx::OnViewDoubleClick.md)|Appelle la commande définie par l'utilisateur lorsque l'utilisateur double\-clique sur n'importe où dans l'application.|  
|[CWinAppEx::OnWorkspaceIdle](../Topic/CWinAppEx::OnWorkspaceIdle.md)||  
|[CWinAppEx::SaveState](../Topic/CWinAppEx::SaveState.md)|Écrit l'état de la zone d'applications au Registre Windows.|  
|[CWinAppEx::SetRegistryBase](../Topic/CWinAppEx::SetRegistryBase.md)|Définit le chemin d'accès de la clé de Registre par défaut.  Cette clé servira racine à tous les appels suivants de Registre.|  
|[CWinAppEx::ShowPopupMenu](../Topic/CWinAppEx::ShowPopupMenu.md)|Affiche un menu contextuel.|  
|[CWinAppEx::WriteBinary](../Topic/CWinAppEx::WriteBinary.md)|Écrit les données binaires à la valeur de Registre spécifiée.|  
|[CWinAppEx::WriteInt](../Topic/CWinAppEx::WriteInt.md)|Écrit les données numériques à la valeur de Registre spécifiée.|  
|[CWinAppEx::WriteObject](../Topic/CWinAppEx::WriteObject.md)|Écrit les données dérivées de [CObject Class](../../mfc/reference/cobject-class.md) à la valeur de Registre spécifiée.|  
|[CWinAppEx::WriteSectionBinary](../Topic/CWinAppEx::WriteSectionBinary.md)|Écrit les données binaires à une valeur de la clé de Registre spécifiée.|  
|[CWinAppEx::WriteSectionInt](../Topic/CWinAppEx::WriteSectionInt.md)|Écrit les données numériques en valeur de la clé de Registre spécifiée.|  
|[CWinAppEx::WriteSectionObject](../Topic/CWinAppEx::WriteSectionObject.md)|Écrit les données dérivées de la classe d' `CObject` à une valeur de la clé de Registre spécifiée.|  
|[CWinAppEx::WriteSectionString](../Topic/CWinAppEx::WriteSectionString.md)|Écrit les données de chaîne en valeur de la clé de Registre spécifiée.|  
|[CWinAppEx::WriteString](../Topic/CWinAppEx::WriteString.md)|Écrit les données de chaîne à la valeur de Registre spécifiée.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CWinAppEx::LoadCustomState](../Topic/CWinAppEx::LoadCustomState.md)|Appelé par l'infrastructure lorsque l'état de l'application a été chargé.|  
|[CWinAppEx::LoadWindowPlacement](../Topic/CWinAppEx::LoadWindowPlacement.md)|Appelé par l'infrastructure lorsqu'il charge la taille et l'emplacement de votre application du Registre.  Les données chargées incluent la taille et l'emplacement du frame principal votre dernier d'application fermé.|  
|[CWinAppEx::OnClosingMainFrame](../Topic/CWinAppEx::OnClosingMainFrame.md)|Appelé par l'infrastructure lorsqu'une fenêtre frame principale gère `WM_CLOSE`.|  
|[CWinAppEx::PreLoadState](../Topic/CWinAppEx::PreLoadState.md)|Appelé par l'infrastructure immédiatement avant l'état de l'application est chargé.|  
|[CWinAppEx::PreSaveState](../Topic/CWinAppEx::PreSaveState.md)|Appelé par l'infrastructure immédiatement avant l'état de l'application est enregistré.|  
|[CWinAppEx::ReloadWindowPlacement](../Topic/CWinAppEx::ReloadWindowPlacement.md)|Recharge la taille et l'emplacement de la fenêtre fournie du Registre|  
|[CWinAppEx::SaveCustomState](../Topic/CWinAppEx::SaveCustomState.md)|Appelé par l'infrastructure après son écrire l'état de l'application au Registre.|  
|[CWinAppEx::StoreWindowPlacement](../Topic/CWinAppEx::StoreWindowPlacement.md)|Appelé par l'infrastructure pour écrire la taille et l'emplacement du frame principal au Registre.|  
  
### Membres de données  
  
|Nom|Description|  
|---------|-----------------|  
|[CWinAppEx::m\_bForceImageReset](../Topic/CWinAppEx::m_bForceImageReset.md)|Spécifie si l'infrastructure remettra à l'état initial toutes les images de barre d'outils de la fenêtre frame qui contient la barre d'outils est chargée.|  
  
## Notes  
 Une grande partie de la fonctionnalité fournie par l'infrastructure MFC dépend de la classe d' `CWinAppEx` .  Vous pouvez incorporer la classe d' `CWinAppEx` à votre application de deux façons :  
  
-   Construisez une classe d' `CWinAppEx` dans le thread principal.  
  
-   Dérivez la classe d'application principale d' `CWinAppEx`.  
  
 Après avoir incorporiez `CWinAppEx` à votre application, vous pouvez initialiser de n'importe lequel des gestionnaires d'application.  Avant d'utiliser un gestionnaire d'application, vous devez l'initialisation en appelant le approprié initialisez la méthode.  Pour obtenir un pointeur vers un gestionnaire spécifique, appelez la méthode associée get.  La classe d' `CWinAppEx` gère les gestionnaires d'application suivants : [CMouseManager Class](../../mfc/reference/cmousemanager-class.md), [CContextMenuManager Class](../../mfc/reference/ccontextmenumanager-class.md), [CKeyboardManager Class](../../mfc/reference/ckeyboardmanager-class.md), [CUserToolsManager Class](../../mfc/reference/cusertoolsmanager-class.md), et [CMenuTearOffManager Class](../../mfc/reference/cmenutearoffmanager-class.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 [CWinApp](../../mfc/reference/cwinapp-class.md)  
  
 [CWinAppEx](../../mfc/reference/cwinappex-class.md)  
  
## Configuration requise  
 **en\-tête :** afxwinappex.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CWinApp Class](../../mfc/reference/cwinapp-class.md)   
 [CMouseManager Class](../../mfc/reference/cmousemanager-class.md)   
 [CContextMenuManager Class](../../mfc/reference/ccontextmenumanager-class.md)   
 [CKeyboardManager Class](../../mfc/reference/ckeyboardmanager-class.md)   
 [CUserToolsManager Class](../../mfc/reference/cusertoolsmanager-class.md)