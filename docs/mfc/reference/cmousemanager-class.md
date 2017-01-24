---
title: "CMouseManager Class | Microsoft Docs"
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
  - "CMouseManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMouseManager class"
ms.assetid: a4d05017-4e44-4a40-8b57-4ece0de20481
caps.latest.revision: 26
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMouseManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Permet à un utilisateur aux différents ordres d'associé à un objet particulier de [CView](../../mfc/reference/cview-class.md) lorsque l'utilisateur double\-clique sur l'intérieur qui s'affichent.  
  
## Syntaxe  
  
```  
class CMouseManager : public CObject  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMouseManager::AddView](../Topic/CMouseManager::AddView.md)|Ajoute un objet d' `CView` à la boîte de dialogue **Personnalisation** .  La boîte de dialogue **Personnalisation** permet à l'utilisateur d'associer un double\-clic avec une commande pour chacune des vues répertoriées.|  
|[CMouseManager::GetViewDblClickCommand](../Topic/CMouseManager::GetViewDblClickCommand.md)|Retourne la commande exécutée lorsque l'utilisateur double\-clique sur l'intérieur de la vue fournie.|  
|[CMouseManager::GetViewIconId](../Topic/CMouseManager::GetViewIconId.md)|Retourne l'icône associée à l'identification fournies de vue|  
|[CMouseManager::GetViewIdByName](../Topic/CMouseManager::GetViewIdByName.md)|Retourne l'ID de vue associé au nom de la vue fourni.|  
|[CMouseManager::GetViewNames](../Topic/CMouseManager::GetViewNames.md)|Extrait une liste de tous les noms de vues ajoutés.|  
|[CMouseManager::LoadState](../Topic/CMouseManager::LoadState.md)|Charge l'état d' `CMouseManager` du Registre Windows.|  
|[CMouseManager::SaveState](../Topic/CMouseManager::SaveState.md)|Écrit l'état d' `CMouseManager` au Registre Windows.|  
|[CMouseManager::SetCommandForDblClk](../Topic/CMouseManager::SetCommandForDblClk.md)|Associe la commande fourni et la vue fournie.|  
  
## Notes  
 La classe d' `CMouseManager` gère une collection d'objets d' `CView` .  Chaque vue est identifiée par un nom et par un ID  Ces vues sont affichées dans la boîte de dialogue **Personnalisation** .  L'utilisateur peut modifier la commande associée à un affichage via la boîte de dialogue **Personnalisation** .  La commande associée est exécutée lorsque l'utilisateur double\-clique dans cette vue.  Pour prendre en charge cette opération d'un point de vue de l'encodage, vous devez traiter le message d' `WM_LBUTTONDBLCLK` et appeler la fonction de [CWinAppEx::OnViewDoubleClick](../Topic/CWinAppEx::OnViewDoubleClick.md) dans le code de cet objet d' `CView` .  
  
 Vous ne devez pas créer un objet d' `CMouseManager` manuellement.  Il est créé par l'infrastructure de votre application.  Il également sera perdu automatiquement lorsque l'utilisateur quitte l'application.  Pour obtenir un pointeur vers le gestionnaire de la souris pour votre application, appelez [CWinAppEx::GetMouseManager](../Topic/CWinAppEx::GetMouseManager.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMouseManager](../../mfc/reference/cmousemanager-class.md)  
  
## Configuration requise  
 **en\-tête :** afxmousemanager.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)   
 [Personnalisation du clavier et de la souris](../../mfc/keyboard-and-mouse-customization.md)