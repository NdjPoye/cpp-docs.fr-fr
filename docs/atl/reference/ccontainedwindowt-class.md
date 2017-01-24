---
title: "CContainedWindowT Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CContainedWindow"
  - "CContainedWindowT"
  - "ATL.CContainedWindowT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CContainedWindow class"
  - "CContainedWindowT class"
  - "contained windows"
ms.assetid: cde0ca36-9347-4068-995a-d294dae57ca9
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CContainedWindowT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente une fenêtre contenue dans un autre objet.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
      template <  
class TBase= CWindow,  
class TWinTraits= CControlWinTraits   
>  
class CContainedWindowT :  
public TBase  
```  
  
#### Paramètres  
 *TBase*  
 La classe de base de votre nouvelle classe.  La classe de base par défaut est `CWindow`.  
  
 `TWinTraits`  
 Une classe Ctraits qui définit des styles pour votre fenêtre.  La valeur par défaut est `CControlWinTraits`.  
  
> [!NOTE]
>  [CContainedWindow](../Topic/CContainedWindow.md) est une spécialisation d' `CContainedWindowT`.  Si vous souhaitez modifier la classe de base ou caractéristiques, utilisez `CContainedWindowT` directement.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CContainedWindowT::CContainedWindowT](../Topic/CContainedWindowT::CContainedWindowT.md)|Constructeur.  Initialise les données membres pour spécifier la table des messages traitera les messages de la fenêtre contenue.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CContainedWindowT::Create](../Topic/CContainedWindowT::Create.md)|Crée une fenêtre.|  
|[CContainedWindowT::DefWindowProc](../Topic/CContainedWindowT::DefWindowProc.md)|Fournit le traitement des messages par défaut.|  
|[CContainedWindowT::GetCurrentMessage](../Topic/CContainedWindowT::GetCurrentMessage.md)|Retourne le message actuel.|  
|[CContainedWindowT::RegisterWndSuperclass](../Topic/CContainedWindowT::RegisterWndSuperclass.md)|Stocke la classe de fenêtre de la fenêtre contenue.|  
|[CContainedWindowT::SubclassWindow](../Topic/CContainedWindowT::SubclassWindow.md)|Sous\-classes une fenêtre.|  
|[CContainedWindowT::SwitchMessageMap](../Topic/CContainedWindowT::SwitchMessageMap.md)|Remplace la table des messages est utilisée pour traiter les messages de la fenêtre contenue.|  
|[CContainedWindowT::UnsubclassWindow](../Topic/CContainedWindowT::UnsubclassWindow.md)|Restaure une fenêtre précédemment sous\-classée.|  
|[CContainedWindowT::WindowProc](../Topic/CContainedWindowT::WindowProc.md)|\(Statique\) traite les messages envoyés à la fenêtre contenue.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CContainedWindowT::m\_dwMsgMapID](../Topic/CContainedWindowT::m_dwMsgMapID.md)|Identifie la table des messages traitera les messages de la fenêtre contenue.|  
|[CContainedWindowT::m\_lpszClassName](../Topic/CContainedWindowT::m_lpszClassName.md)|Spécifie le nom d'une classe de fenêtre existante sur laquelle une nouvelle classe de fenêtre est basée.|  
|[CContainedWindowT::m\_pfnSuperWindowProc](../Topic/CContainedWindowT::m_pfnSuperWindowProc.md)|Points à la procédure de fenêtre d'origine de la classe de fenêtre.|  
|[CContainedWindowT::m\_pObject](../Topic/CContainedWindowT::m_pObject.md)|Pointe vers l'objet contenant.|  
  
## Notes  
 `CContainedWindowT` implémente une fenêtre contenue dans un autre objet.  Utilisations de la procédure de fenêtre d'`CContainedWindowT` une table des messages dans l'objet contenant des messages directs aux gestionnaires appropriés.  Lorsque vous construisez un objet d' `CContainedWindowT` , vous spécifiez la table des messages doit être utilisée.  
  
 `CContainedWindowT` vous permet de créer une nouvelle fenêtre par superclassing une classe de fenêtre existante.  La méthode de **Créer** enregistre tout d'abord une classe de fenêtre qui est basé sur une classe existante mais utilise `CContainedWindowT::WindowProc`.  **Créer** crée ensuite une fenêtre sur cette nouvelle classe de fenêtre.  Chaque instance d' `CContainedWindowT` peuvent surclassement la une classe de fenêtre différente.  
  
 `CContainedWindowT` prend également en charge le sous\-classement de fenêtre.  La méthode d' `SubclassWindow` attaché une fenêtre existante à l'objet d' `CContainedWindowT` et modifie la procédure de fenêtre par `CContainedWindowT::WindowProc`.  Chaque instance d' `CContainedWindowT` peuvent la sous\-classe une autre fenêtre.  
  
> [!NOTE]
>  Pour tout objet donné d' `CContainedWindowT` , appelez **Créer** ou `SubclassWindow`.  Vous ne devez pas appeler les deux méthodes sur le même objet.  
  
 Lorsque vous utilisez l'option pour **Add control based on** dans l'Assistant Projet ATL, l'assistant ajoute automatiquement une donnée membre d' `CContainedWindowT` à la classe implémentant le contrôle.  l'exemple suivant montre comment la fenêtre contenue est déclarée :  
  
 [!code-cpp[NVC_ATL_Windowing#38](../../atl/codesnippet/CPP/ccontainedwindowt-class_1.h)]  
  
 [!code-cpp[NVC_ATL_Windowing#39](../../atl/codesnippet/CPP/ccontainedwindowt-class_2.h)]  
  
 [!code-cpp[NVC_ATL_Windowing#40](../../atl/codesnippet/CPP/ccontainedwindowt-class_3.h)]  
  
|Pour plus d'informations sur le sujet suivant|Consultez|  
|---------------------------------------------------|---------------|  
|Créer des contrôles|[Didacticiel ATL](../../atl/active-template-library-atl-tutorial.md)|  
|À l'aide de windows dans ATL|[Classes de fenêtres ATL](../../atl/atl-window-classes.md)|  
|L'Assistant Projet ATL|[Création d'un projet ATL](../../atl/reference/creating-an-atl-project.md)|  
|Windows|[fenêtres](http://msdn.microsoft.com/library/windows/desktop/ms632595) et sujets suivants dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]|  
  
## Hiérarchie d'héritage  
 `TBase`  
  
 `CContainedWindowT`  
  
## Configuration requise  
 **Header:** atlwin.h  
  
## Voir aussi  
 [CWindow Class](../../atl/reference/cwindow-class.md)   
 [CWindowImpl Class](../../atl/reference/cwindowimpl-class.md)   
 [CMessageMap Class](../../atl/reference/cmessagemap-class.md)   
 [BEGIN\_MSG\_MAP](../Topic/BEGIN_MSG_MAP.md)   
 [ALT\_MSG\_MAP](../Topic/ALT_MSG_MAP.md)   
 [Class Overview](../../atl/atl-class-overview.md)