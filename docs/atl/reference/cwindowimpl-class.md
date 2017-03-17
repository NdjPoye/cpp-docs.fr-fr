---
title: Classe de CWindowImpl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWindowImpl
- ATLWIN/ATL::CWindowImpl
- ATLWIN/ATL::CWindowImpl::Create
- ATLWIN/ATL::DefWindowProc
- ATLWIN/ATL::GetCurrentMessage
- ATLWIN/ATL::GetWindowProc
- ATLWIN/ATL::OnFinalMessage
- ATLWIN/ATL::SubclassWindow
- ATLWIN/ATL::UnsubclassWindow
- ATLWIN/ATL::GetWndClassInfo
- ATLWIN/ATL::WindowProc
- ATLWIN/ATL::m_pfnSuperWindowProc
dev_langs:
- C++
helpviewer_keywords:
- CWindowImpl class
- subclassing windows, ATL
ms.assetid: 02eefd45-a0a6-4d1b-99f6-dbf627e2cc2f
caps.latest.revision: 22
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 76827682e96d2aea80880fa7d70c267abe02ee1c
ms.lasthandoff: 02/24/2017

---
# <a name="cwindowimpl-class"></a>CWindowImpl (classe)
Fournit des méthodes pour créer ou sous-classer une fenêtre.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class T, class TBase = CWindow, class TWinTraits = CControlWinTraits>  
class ATL_NO_VTABLE CWindowImpl : public CWindowImplBaseT<TBase, TWinTraits>
```    
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Votre nouvelle classe, dérivée de `CWindowImpl`.  
  
 *TBase*  
 Classe de base de votre classe. Par défaut, la classe de base est [CWindow](../../atl/reference/cwindow-class.md).  
  
 `TWinTraits`  
 A [classe de traits](../../atl/understanding-window-traits.md) qui définit les styles de votre fenêtre. La valeur par défaut est `CControlWinTraits`.  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CWindowImpl::Create](#create)|Crée une fenêtre.|  
  
### <a name="cwindowimplbaset-methods"></a>Méthodes CWindowImplBaseT  
  
|||  
|-|-|  
|[DefWindowProc](#defwindowproc)|Fournit le traitement du message par défaut.|  
|[GetCurrentMessage](#getcurrentmessage)|Retourne le message actuel.|  
|[GetWindowProc](#getwindowproc)|Retourne la procédure de fenêtre active.|  
|[OnFinalMessage](#onfinalmessage)|Appelée après réception du dernier message (généralement `WM_NCDESTROY`).|  
|[SubclassWindow](#subclasswindow)|Sous-classe une fenêtre.|  
|[UnsubclassWindow](#unsubclasswindow)|Restaure une fenêtre précédemment sous-classée.|  
  
### <a name="static-methods"></a>Méthodes statiques  
  
|||  
|-|-|  
|[GetWndClassInfo](#getwndclassinfo)|Retourne une instance statique de [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md), qui gère les informations de classe de fenêtre.|  
|[WindowProc](#windowproc)|Traite les messages envoyés à la fenêtre.|  
  
### <a name="data-members"></a>Membres de données  
  
|||  
|-|-|  
|[m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|Pointe vers la procédure de fenêtre d'origine de la classe de fenêtre.|  
  
## <a name="remarks"></a>Notes  
 Vous pouvez utiliser `CWindowImpl` pour créer une fenêtre ou sous-classer une fenêtre existante. le `CWindowImpl` procédure de fenêtre utilise une table des messages pour diriger les messages vers les gestionnaires appropriés.  
  
 `CWindowImpl::Create`Crée une fenêtre basée sur les informations de classe de fenêtre qui sont gérées par [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md). `CWindowImpl`contient le [DECLARE_WND_CLASS](http://msdn.microsoft.com/library/55247a72-fb9e-4bde-87f3-747c08076971) (macro), ce qui signifie que `CWndClassInfo` enregistre une nouvelle classe de fenêtre. Si vous souhaitez surclasser une classe de fenêtre existante, dérivez votre classe de `CWindowImpl` et incluent la [DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd) (macro). Dans ce cas, `CWndClassInfo` enregistre une classe de fenêtre basée sur une classe existante mais utilise `CWindowImpl::WindowProc`. Exemple :  
  
 [!code-cpp[NVC_ATL_Windowing&#43;](../../atl/codesnippet/cpp/cwindowimpl-class_1.h)]  
  
> [!NOTE]
>  Étant donné que `CWndClassInfo` gère les informations d'une seule classe de fenêtre, chaque fenêtre créée via une instance de `CWindowImpl` est basée sur la même classe de fenêtre.  
  
 `CWindowImpl` prend également en charge le sous-classement de fenêtre. La méthode `SubclassWindow` attache une fenêtre existante à l'objet `CWindowImpl` et remplace la procédure de fenêtre par `CWindowImpl::WindowProc`. Chaque instance de `CWindowImpl` peut sous-classer une fenêtre différente.  
  
> [!NOTE]
>  Des `CWindowImpl` de l’objet, appelez **créer** ou `SubclassWindow`. N'appelez pas les deux méthodes sur le même objet.  
  
 En plus de `CWindowImpl`, ATL fournit [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) pour créer une fenêtre qui est contenue dans un autre objet.  
  
 Le destructeur de classe de base (~ **CWindowImplRoot**) garantit que la fenêtre disparaît avant la destruction de l’objet.  
  
 `CWindowImpl`dérive de **CWindowImplBaseT**, qui dérive de **CWindowImplRoot**, qui dérive de **TBase** et [CMessageMap](../../atl/reference/cmessagemap-class.md).  
  
|Pour plus d'informations sur|Voir|  
|--------------------------------|---------|  
|Création de contrôles|[ATL (didacticiel)](../../atl/active-template-library-atl-tutorial.md)|  
|Utilisation de fenêtres dans ATL|[Classes de fenêtre ATL](../../atl/atl-window-classes.md)|  
|Assistant Projet ATL|[Création d’un projet ATL](../../atl/reference/creating-an-atl-project.md)|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CMessageMap](../../atl/reference/cmessagemap-class.md)  
  
 `TBase`  
  
 `CWindowImplRoot`  
  
 `CWindowImplBaseT`  
  
 `CWindowImpl`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h  
  
##  <a name="create"></a>CWindowImpl::Create  
 Crée une fenêtre basée sur une nouvelle classe de fenêtre.  
  
```
HWND Create(
    HWND hWndParent,
    _U_RECT rect = NULL,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `hWndParent`  
 [in] Handle de la fenêtre parente ou propriétaire.  
  
 `rect`  
 [in] A [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure spécifiant la position de la fenêtre. Les `RECT` peuvent être passés par le pointeur ou par référence.  
  
 `szWindowName`  
 [in] Spécifie le nom de la fenêtre. La valeur par défaut est **NULL**.  
  
 `dwStyle`  
 [in] Le style de la fenêtre. Cette valeur est combinée avec le style fourni par la classe de traits pour la fenêtre. La valeur par défaut donne les caractéristiques de classe un contrôle total sur le style. Pour obtenir la liste des valeurs possibles, consultez la page [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwExStyle`  
 [in] Le style de fenêtre étendus. Cette valeur est combinée avec le style fourni par la classe de traits pour la fenêtre. La valeur par défaut donne les caractéristiques de classe un contrôle total sur le style. Pour obtenir la liste des valeurs possibles, consultez la page [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `MenuOrID`  
 [in] Pour une fenêtre enfant, l’identificateur de la fenêtre. Pour une fenêtre de niveau supérieur, un descripteur de menu de la fenêtre. La valeur par défaut est **0 u**.  
  
 `lpCreateParam`  
 [in] Pointeur vers les données de création de fenêtre. Pour une description complète, consultez la description pour le paramètre final [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680).  
  
### <a name="return-value"></a>Valeur de retour  
 Si l’opération réussit, le descripteur de la fenêtre nouvellement créé. Dans le cas contraire, **NULL**.  
  
### <a name="remarks"></a>Remarques  
 **Créer** s’enregistre d’abord la classe de fenêtre si elle n’a pas encore été enregistré. La fenêtre nouvellement créée est automatiquement joint à la `CWindowImpl` objet.  
  
> [!NOTE]
>  N’appelez pas **créer** si vous avez déjà appelé [SubclassWindow](#subclasswindow).  
  
 Pour utiliser une classe de fenêtre basée sur une classe de fenêtre existante, dérivez votre classe de `CWindowImpl` et incluent la [DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd) (macro). Procédure de fenêtre de la classe de fenêtre existante est enregistrée dans [m_pfnSuperWindowProc](#m_pfnsuperwindowproc). Pour plus d’informations, consultez la [CWindowImpl](../../atl/reference/cwindowimpl-class.md) vue d’ensemble.  
  
> [!NOTE]
>  Si 0 est utilisée comme valeur pour le `MenuOrID` paramètre, il doit être spécifié en tant que 0 u (valeur par défaut) pour éviter une erreur du compilateur.  
  
##  <a name="defwindowproc"></a>CWindowImpl::DefWindowProc  
 Appelé par [WindowProc](#windowproc) pour traiter les messages non gérées par la table des messages.  
  
```
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);

LRESULT DefWindowProc();
```  
  
### <a name="parameters"></a>Paramètres  
 `uMsg`  
 [in] Le message est envoyé à la fenêtre.  
  
 `wParam`  
 [in] Spécifique au message des informations supplémentaires.  
  
 `lParam`  
 [in] Spécifique au message des informations supplémentaires.  
  
### <a name="return-value"></a>Valeur de retour  
 Le résultat du traitement du message.  
  
### <a name="remarks"></a>Notes  
 Par défaut, `DefWindowProc` appelle la [CallWindowProc](http://msdn.microsoft.com/library/windows/desktop/ms633571) fonction Win32 pour envoyer les informations de message à la procédure spécifiée dans [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
 La fonction sans paramètre récupère automatiquement les paramètres nécessaires à partir du message en cours.  
  
##  <a name="getcurrentmessage"></a>CWindowImpl::GetCurrentMessage  
 Retourne le message actuel, empaqueté dans la `MSG` structure.  
  
```
const MSG* GetCurrentMessage();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le message en cours.  
  
##  <a name="getwindowproc"></a>CWindowImpl::GetWindowProc  
 Retourne `WindowProc`, la procédure de fenêtre en cours.  
  
```
virtual WNDPROC GetWindowProc();
```  
  
### <a name="return-value"></a>Valeur de retour  
 La procédure de fenêtre en cours.  
  
### <a name="remarks"></a>Remarques  
 Substituez cette méthode pour remplacer la procédure de fenêtre par les vôtres.  
  
##  <a name="getwndclassinfo"></a>CWindowImpl::GetWndClassInfo  
 Appelé par [créer](#create) pour accéder aux informations de classe de fenêtre.  
  
```
static CWndClassInfo& GetWndClassInfo();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une instance statique de [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md).  
  
### <a name="remarks"></a>Remarques  
 Par défaut, `CWindowImpl` obtient cette méthode via la [DECLARE_WND_CLASS](http://msdn.microsoft.com/library/55247a72-fb9e-4bde-87f3-747c08076971) macro, qui spécifie une nouvelle classe de fenêtre.  
  
 Pour surclasser une classe de fenêtre existante, dérivez votre classe de `CWindowImpl` et incluent la [DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd) macro pour remplacer `GetWndClassInfo`. Pour plus d’informations, consultez la [CWindowImpl](../../atl/reference/cwindowimpl-class.md) vue d’ensemble.  
  
 Outre l’utilisation de la `DECLARE_WND_CLASS` et `DECLARE_WND_SUPERCLASS` macros, vous pouvez remplacer `GetWndClassInfo` par votre propre implémentation.  
  
##  <a name="m_pfnsuperwindowproc"></a>CWindowImpl::m_pfnSuperWindowProc  
 En fonction de la fenêtre, pointe vers une des procédures suivantes de fenêtre.  
  
```
WNDPROC m_pfnSuperWindowProc;
```  
  
### <a name="remarks"></a>Remarques  
  
|Type de fenêtre|Procédure de fenêtre|  
|--------------------|----------------------|  
|Une fenêtre basée sur une nouvelle classe de fenêtre, spécifiée par le biais du [DECLARE_WND_CLASS](http://msdn.microsoft.com/library/55247a72-fb9e-4bde-87f3-747c08076971) macro.|Le [DefWindowProc](http://msdn.microsoft.com/library/windows/desktop/ms633572) fonction Win32.|  
|Une fenêtre basée sur une classe de fenêtre qui modifie une classe existante, spécifiée par le biais du [DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd) (macro).|Procédure de fenêtre de la classe de fenêtre existante.|  
|Une fenêtre sous-classée.|Procédure de fenêtre d’origine de la fenêtre sous-classée.|  
  
 [CWindowImpl::DefWindowProc](#defwindowproc) envoie un message d’informations à la procédure enregistrée dans `m_pfnSuperWindowProc`.  
  
##  <a name="onfinalmessage"></a>CWindowImpl::OnFinalMessage  
 Appelé après la réception du dernier message (généralement `WM_NCDESTROY`).  
  
```
virtual void OnFinalMessage(HWND hWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 `hWnd`  
 [in] Handle vers la fenêtre en cours de destruction.  
  
### <a name="remarks"></a>Remarques  
 L’implémentation par défaut de `OnFinalMessage` ne fait rien, mais vous pouvez remplacer cette fonction pour traiter de nettoyage avant la destruction d’une fenêtre. Si vous souhaitez supprimer automatiquement votre objet lors de la destruction de la fenêtre, vous pouvez appeler `delete this;` dans cette fonction.  
  
##  <a name="subclasswindow"></a>CWindowImpl::SubclassWindow  
 La fenêtre est identifiée par les sous-classes `hWnd` et l’attache à le `CWindowImpl` objet.  
  
```
BOOL SubclassWindow(HWND hWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 `hWnd`  
 [in] Handle de la fenêtre sous-classée.  
  
### <a name="return-value"></a>Valeur de retour  
 **TRUE** si la fenêtre a été sous-classé ; sinon, **FALSE**.  
  
### <a name="remarks"></a>Remarques  
 La fenêtre sous-classée utilise désormais [CWindowImpl::WindowProc](#windowproc). La procédure de fenêtre d’origine est enregistrée dans [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
> [!NOTE]
>  N’appelez pas `SubclassWindow` si vous avez déjà appelé [créer](#create).  
  
##  <a name="unsubclasswindow"></a>CWindowImpl::UnsubclassWindow  
 Détache la fenêtre sous-classé à partir de la `CWindowImpl` de l’objet et restaure la procédure de fenêtre d’origine, enregistrée dans [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
```
HWND UnsubclassWindow();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Handle de la fenêtre précédemment sous-classée.  
  
##  <a name="windowproc"></a>CWindowImpl::WindowProc  
 Cette fonction statique implémente la procédure de fenêtre.  
  
```
static LRESULT CALLBACK WindowProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Paramètres  
 `hWnd`  
 [in] Handle de la fenêtre.  
  
 `uMsg`  
 [in] Le message est envoyé à la fenêtre.  
  
 `wParam`  
 [in] Spécifique au message des informations supplémentaires.  
  
 `lParam`  
 [in] Spécifique au message des informations supplémentaires.  
  
### <a name="return-value"></a>Valeur de retour  
 Le résultat du traitement du message.  
  
### <a name="remarks"></a>Notes  
 `WindowProc`utilise la table des messages par défaut (déclaré avec [BEGIN_MSG_MAP](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554)) pour diriger les messages vers les gestionnaires appropriés. Si nécessaire, `WindowProc` appelle [DefWindowProc](#defwindowproc) pour le traitement des messages supplémentaires. Si le message final n’est pas géré, `WindowProc` effectue les opérations suivantes :  
  
-   Exécute unsubclassing si la fenêtre a été unsubclassed.  
  
-   Efface `m_hWnd`.  
  
-   Appels [OnFinalMessage](#onfinalmessage) avant la destruction de la fenêtre.  
  
 Vous pouvez substituer `WindowProc` pour fournir un autre mécanisme de gestion des messages.  
  
## <a name="see-also"></a>Voir aussi  
 [BEGIN_MSG_MAP](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554)   
 [CComControl (classe)](../../atl/reference/ccomcontrol-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

