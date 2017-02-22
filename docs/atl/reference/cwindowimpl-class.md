---
title: "CWindowImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CWindowImpl"
  - "ATL.CWindowImpl"
  - "CWindowImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWindowImpl class"
  - "subclassing windows, ATL"
ms.assetid: 02eefd45-a0a6-4d1b-99f6-dbf627e2cc2f
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CWindowImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit des méthodes pour la création ou le sous\-classement une fenêtre.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans des applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Syntaxe  
  
```  
  
      template <  
class T,  
class TBase= CWindow,  
class TWinTraits= CControlWinTraits   
>  
class ATL_NO_VTABLE CWindowImpl :  
public CWindowImplBaseT< TBase, TWinTraits>  
```  
  
#### Paramètres  
 `T`  
 Votre nouvelle classe, dérivée de `CWindowImpl`.  
  
 *TBase*  
 La classe de base de votre classe.  Par défaut, la classe de base est [CWindow](../../atl/reference/cwindow-class.md).  
  
 `TWinTraits`  
 Une [classe traits](../../atl/understanding-window-traits.md) qui définit des styles pour votre fenêtre.  La valeur par défaut est `CControlWinTraits`.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CWindowImpl::Create](../Topic/CWindowImpl::Create.md)|Crée une fenêtre.|  
  
### Méthodes de CWindowImplBaseT  
  
|||  
|-|-|  
|[DefWindowProc](../Topic/CWindowImpl::DefWindowProc.md)|Fournit le traitement du message par défaut.|  
|[GetCurrentMessage](../Topic/CWindowImpl::GetCurrentMessage.md)|Retourne le message actuel.|  
|[GetWindowProc](../Topic/CWindowImpl::GetWindowProc.md)|Retourne la procédure de fenêtre active.|  
|[OnFinalMessage](../Topic/CWindowImpl::OnFinalMessage.md)|Appelé après le dernier message est reçu \(généralement `WM_NCDESTROY`\).|  
|[SubclassWindow](../Topic/CWindowImpl::SubclassWindow.md)|sous\-classement d'une fenêtre.|  
|[UnsubclassWindow](../Topic/CWindowImpl::UnsubclassWindow.md)|Restaure une fenêtre précédemment sous\-classée.|  
  
### Méthodes statiques  
  
|||  
|-|-|  
|[GetWndClassInfo](../Topic/CWindowImpl::GetWndClassInfo.md)|Retourne une instance statique de [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md), qui gère des informations de classe de fenêtre.|  
|[WindowProc](../Topic/CWindowImpl::WindowProc.md)|Traite les messages envoyés à la fenêtre.|  
  
### Membres de données  
  
|||  
|-|-|  
|[m\_pfnSuperWindowProc](../Topic/CWindowImpl::m_pfnSuperWindowProc.md)|Pointe vers la procédure de fenêtre d'origine de la classe de fenêtre.|  
  
## Notes  
 Utilisez `CWindowImpl` pour créer une fenêtre ou une sous\-classe d'une fenêtre existante. la procédure de fenêtre `CWindowImpl` utilise une table des messages pour exécuter les messages aux gestionnaires appropriés.  
  
 `CWindowImpl::Create` crée une fenêtre selon les informations de classe de fenêtre gérées par [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md).  `CWindowImpl` contient la macro [DECLARE\_WND\_CLASS](../Topic/DECLARE_WND_CLASS.md), qui signifie que `CWndClassInfo` enregistre une nouvelle classe de fenêtre.  Si vous souhaitez surclasser une classe de fenêtre existante, dérivez votre classe de `CWindowImpl` et incluez la macro de [DECLARE\_WND\_SUPERCLASS](../Topic/DECLARE_WND_SUPERCLASS.md).  Dans ce cas, `CWndClassInfo` signale une classe de fenêtre basée sur une classe existante mais utilise `CWindowImpl::WindowProc`.  Par exemple :  
  
 [!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/CPP/cwindowimpl-class_1.h)]  
  
> [!NOTE]
>  Comme `CWndClassInfo` gère les informations pour une seule classe de fenêtre, chaque fenêtre créée via une instance `CWindowImpl` est basé sur la même classe de fenêtre.  
  
 `CWindowImpl` prend également en charge le sous\-classement de fenêtre.  La méthode `SubclassWindow` attaché une fenêtre existante à l'objet `CWindowImpl` et modifie la procédure de fenêtre en `CWindowImpl::WindowProc`.  Chaque instance de `CWindowImpl` peut fournir la sous\-classe une autre fenêtre.  
  
> [!NOTE]
>  Pour tout objet `CWindowImpl` donné, appelez **Créer** ou `SubclassWindow`.  N'appelez pas les deux méthodes sur le même objet.  
  
 En plus de `CWindowImpl`, ATL fournit [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) pour créer une fenêtre qui est contenue dans un autre objet.  
  
 Le destructeur de classe de base \(~**CWindowImplRoot**\) garantit que la fenêtre est partie avant que l'objet soit détruit.  
  
 `CWindowImpl` dérive de **CWindowImplBaseT**, qui dérive de **CWindowImplRoot**, qui dérive de **TBase** et [CMessageMap](../../atl/reference/cmessagemap-class.md).  
  
|Pour plus d'informations sur le sujet suivant|Consultez|  
|---------------------------------------------------|---------------|  
|Créer des contrôles|[Didacticiel ATL](../../atl/active-template-library-atl-tutorial.md)|  
|Utilisation des fenêtres dans ATL|[ATL, classes de fenêtre](../../atl/atl-window-classes.md)|  
|Assistant Projet ATL|[Création d'un projet ATL](../../atl/reference/creating-an-atl-project.md)|  
  
## Hiérarchie d'héritage  
 [CMessageMap](../../atl/reference/cmessagemap-class.md)  
  
 `TBase`  
  
 `CWindowImplRoot`  
  
 `CWindowImplBaseT`  
  
 `CWindowImpl`  
  
## Configuration requise  
 **En\-tête:** afxwin.h  
  
## Voir aussi  
 [BEGIN\_MSG\_MAP](../Topic/BEGIN_MSG_MAP.md)   
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)