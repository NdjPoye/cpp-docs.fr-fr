---
title: "CContextMenuManager Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CContextMenuManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CContextMenuManager class"
ms.assetid: 1de20640-243c-47e1-85de-1baa4153bc83
caps.latest.revision: 32
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 33
---
# CContextMenuManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'objet d' `CContextMenuManager` gère des menus contextuels, également appelé des menus contextuels.  
  
## Syntaxe  
  
```  
class CContextMenuManager : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CContextMenuManager::CContextMenuManager](../Topic/CContextMenuManager::CContextMenuManager.md)|Construit un objet `CContextMenuManager`.|  
|`CContextMenuManager::~CContextMenuManager`|Destructor.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CContextMenuManager::AddMenu](../Topic/CContextMenuManager::AddMenu.md)|Ajoute un nouveau menu contextuel.|  
|[CContextMenuManager::GetMenuById](../Topic/CContextMenuManager::GetMenuById.md)|Retourne un handle vers le menu associé à l'identification fournies de ressource|  
|[CContextMenuManager::GetMenuByName](../Topic/CContextMenuManager::GetMenuByName.md)|Retourne un handle au menu qui correspond au nom de menu fourni.|  
|[CContextMenuManager::GetMenuNames](../Topic/CContextMenuManager::GetMenuNames.md)|Retourne une liste de noms de menu.|  
|[CContextMenuManager::LoadState](../Topic/CContextMenuManager::LoadState.md)|Charge des menus contextuels inscrits dans le Registre Windows.|  
|[CContextMenuManager::ResetState](../Topic/CContextMenuManager::ResetState.md)|Efface les menus contextuels du gestionnaire de menu contextuel.|  
|[CContextMenuManager::SaveState](../Topic/CContextMenuManager::SaveState.md)|Enregistre les menus contextuels au Registre Windows.|  
|[CContextMenuManager::SetDontCloseActiveMenu](../Topic/CContextMenuManager::SetDontCloseActiveMenu.md)|Contrôle si `CContextMenuManager` ferme le menu contextuel actif lorsqu'il affiche un nouveau menu contextuel.|  
|[CContextMenuManager::ShowPopupMenu](../Topic/CContextMenuManager::ShowPopupMenu.md)|Affiche le menu contextuel spécifié.|  
|[CContextMenuManager::TrackPopupMenu](../Topic/CContextMenuManager::TrackPopupMenu.md)|Affiche le menu contextuel spécifié.  Retourne l'index de la commande de menu sélectionnée.|  
  
## Notes  
 `CContextMenuManager` gère des menus contextuels et vérifie qu'ils ont une apparence cohérente.  
  
 Vous ne devez pas créer un objet d' `CContextMenuManager` manuellement.  l'infrastructure de votre application crée l'objet d' `CContextMenuManager` .  Toutefois, vous devez appeler [CWinAppEx::InitContextMenuManager](../Topic/CWinAppEx::InitContextMenuManager.md) lorsque votre application est initialisée.  Après avoir initialisé le gestionnaire de contexte, utilisez la méthode [CWinAppEx::GetContextMenuManager](../Topic/CWinAppEx::GetContextMenuManager.md) pour obtenir un pointeur vers le gestionnaire de contexte pour votre application.  
  
 Vous pouvez créer des menus contextuels au moment de l'exécution en appelant `AddMenu`.  Si vous souhaitez afficher le menu sans la première entrée d'utilisateur de réception, appelez `ShowPopupMenu`.  `TrackPopupMenu` est utilisé lorsque vous souhaitez créer un menu et une attente l'entrée d'utilisateur.  `TrackPopupMenu` retourne l'index de la commande ou de 0 sélectionnée si l'utilisateur quittait sans sélectionner n'importe quoi.  
  
 `CContextMenuManager` peut également enregistrer et charger son état au Registre Windows.  
  
## Exemple  
 L'exemple suivant montre comment ajouter un menu à un objet d' `CContextMenuManager` , et comment ne pas fermer le menu contextuel actif lorsque l'objet d' `CContextMenuManager` affiche un nouveau menu contextuel.  Cet extrait de code fait partie de [Le personnalisé pages l'exemple](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_CustomPages#4](../../mfc/reference/codesnippet/CPP/ccontextmenumanager-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md)  
  
## Configuration requise  
 **en\-tête :** afxcontextmenumanager.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)   
 [CWinAppEx::InitContextMenuManager](../Topic/CWinAppEx::InitContextMenuManager.md)