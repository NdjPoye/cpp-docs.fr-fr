---
title: Classe de CWndClassInfo | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWndClassInfo
dev_langs:
- C++
helpviewer_keywords:
- CWndClassInfo class
ms.assetid: c36fe7e1-75f1-4cf5-a06f-9f59c43fe6fb
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: f036d79c7a9420e083eb86023c5cbf98906cc1cc
ms.lasthandoff: 02/24/2017

---
# <a name="cwndclassinfo-class"></a>CWndClassInfo (classe)
Cette classe fournit des méthodes pour enregistrer des informations pour une classe de fenêtre.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CWndClassInfo
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|||  
|-|-|  
|[S’inscrire](#register)|Inscrit la classe de fenêtre.|  
  
### <a name="data-members"></a>Membres de données  
  
|||  
|-|-|  
|[m_atom](#m_atom)|Identifie la classe de fenêtre inscrits.|  
|[m_bSystemCursor](#m_bsystemcursor)|Spécifie si la ressource curseur fait référence à un curseur système ou à un curseur contenues dans une ressource de module.|  
|[m_lpszCursorID](#m_lpszcursorid)|Spécifie le nom de la ressource curseur.|  
|[m_lpszOrigName](#m_lpszorigname)|Contient le nom d’une classe de fenêtre existante.|  
|[m_szAutoName](#m_szautoname)|Contient un nom généré par ATL de la classe de fenêtre.|  
|[m_wc](#m_wc)|Conserve les informations de classe de fenêtre dans un **WNDCLASSEX** structure.|  
|[pWndProc](#pwndproc)|Pointe vers la procédure de fenêtre d’une classe de fenêtre existante.|  
  
## <a name="remarks"></a>Notes  
 `CWndClassInfo`gère les informations d’une classe de fenêtre. Vous utilisez généralement `CWndClassInfo` via un des trois macros, `DECLARE_WND_CLASS`, `DECLARE_WND_CLASS_EX`, ou `DECLARE_WND_SUPERCLASS`, comme décrit dans le tableau suivant :  
  
|Macro|Description|  
|-----------|-----------------|  
|[DECLARE_WND_CLASS](http://msdn.microsoft.com/library/55247a72-fb9e-4bde-87f3-747c08076971)|`CWndClassInfo`enregistre des informations pour une nouvelle classe de fenêtre.|  
|[DECLARE_WND_CLASS_EX](http://msdn.microsoft.com/library/0672c144-f2aa-4f6a-ae16-566e3a1f5411)|`CWndClassInfo`enregistre l’information pour une nouvelle classe, y compris les paramètres de classe.|  
|[DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd)|`CWndClassInfo`enregistre des informations pour une classe de fenêtre qui est basée sur une classe existante mais utilise une autre procédure de fenêtre. Cette technique est appelée surclasser.|  
  
 Par défaut, [CWindowImpl](../../atl/reference/cwindowimpl-class.md) inclut la `DECLARE_WND_CLASS` macro pour créer une fenêtre basée sur une nouvelle classe de fenêtre. DECLARE_WND_CLASS fournit les styles par défaut et la couleur d’arrière-plan du contrôle. Si vous souhaitez spécifier le style et la couleur d’arrière-plan vous-même, dérivez votre classe de `CWindowImpl` et incluent la `DECLARE_WND_CLASS_EX` macro dans votre définition de classe.  
  
 Si vous souhaitez créer une fenêtre basée sur une classe de fenêtre existante, dérivez votre classe de `CWindowImpl` et incluent la `DECLARE_WND_SUPERCLASS` macro dans votre définition de classe. Exemple :  
  
 [!code-cpp[NVC_ATL_Windowing&#43;](../../atl/codesnippet/cpp/cwndclassinfo-class_1.h)]  
  
 Pour plus d’informations sur les classes de fenêtre, consultez la page [Classes de fenêtre](http://msdn.microsoft.com/library/windows/desktop/ms632596) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Pour plus d’informations sur l’utilisation des fenêtres dans ATL, consultez l’article [Classes de fenêtre ATL](../../atl/atl-window-classes.md).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h  
  
##  <a name="a-namematoma--cwndclassinfomatom"></a><a name="m_atom"></a>CWndClassInfo::m_atom  
 Contient l’identificateur unique de la classe de fenêtre inscrits.  
  
```
ATOM m_atom;
```  
  
##  <a name="a-namembsystemcursora--cwndclassinfombsystemcursor"></a><a name="m_bsystemcursor"></a>CWndClassInfo::m_bSystemCursor  
 Si **TRUE**, la ressource du système de curseur soit chargée lorsque la classe de fenêtre est enregistrée.  
  
```
BOOL m_bSystemCursor;
```  
  
### <a name="remarks"></a>Notes  
 Sinon, la ressource curseur contenue dans votre module sera chargée.  
  
 `CWndClassInfo`utilise `m_bSystemCursor` uniquement lorsque le [DECLARE_WND_CLASS](http://msdn.microsoft.com/library/55247a72-fb9e-4bde-87f3-747c08076971) (la valeur par défaut dans [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) ou [DECLARE_WND_CLASS_EX](http://msdn.microsoft.com/library/0672c144-f2aa-4f6a-ae16-566e3a1f5411) macro est spécifié. Dans ce cas, `m_bSystemCursor` est initialisée à **TRUE**. Pour plus d’informations, consultez la [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) vue d’ensemble.  
  
##  <a name="a-namemlpszcursorida--cwndclassinfomlpszcursorid"></a><a name="m_lpszcursorid"></a>CWndClassInfo::m_lpszCursorID  
 Spécifie le nom de la ressource curseur ou l’identificateur de ressource dans le mot de poids faible et zéro dans le mot de poids fort.  
  
```
LPCTSTR m_lpszCursorID;
```  
  
### <a name="remarks"></a>Remarques  
 Lorsque la classe de fenêtre est enregistrée, le handle du curseur identifié par `m_lpszCursorID` est récupéré et stockées par [m_wc](#m_wc).  
  
 `CWndClassInfo`utilise `m_lpszCursorID` uniquement lorsque le [DECLARE_WND_CLASS](http://msdn.microsoft.com/library/55247a72-fb9e-4bde-87f3-747c08076971) (la valeur par défaut dans [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) ou [DECLARE_WND_CLASS_EX](http://msdn.microsoft.com/library/0672c144-f2aa-4f6a-ae16-566e3a1f5411) macro est spécifié. Dans ce cas, `m_lpszCursorID` est initialisée à **IDC_ARROW**. Pour plus d’informations, consultez la [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) vue d’ensemble.  
  
##  <a name="a-namemlpszorignamea--cwndclassinfomlpszorigname"></a><a name="m_lpszorigname"></a>CWndClassInfo::m_lpszOrigName  
 Contient le nom d’une classe de fenêtre existante.  
  
```
LPCTSTR m_lpszOrigName;
```  
  
### <a name="remarks"></a>Notes  
 `CWndClassInfo`utilise `m_lpszOrigName` uniquement lorsque vous incluez le [DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd) macro dans votre définition de classe. Dans ce cas, `CWndClassInfo` registres une classe de fenêtre basée sur la classe nommée par `m_lpszOrigName`. Pour plus d’informations, consultez la [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) vue d’ensemble.  
  
##  <a name="a-namemszautonamea--cwndclassinfomszautoname"></a><a name="m_szautoname"></a>CWndClassInfo::m_szAutoName  
 Contient le nom de la classe de fenêtre.  
  
```
TCHAR m_szAutoName[13];
```  
  
### <a name="remarks"></a>Notes  
 `CWndClassInfo`utilise `m_szAutoName` uniquement si **NULL** est transmis pour le `WndClassName` paramètre [DECLARE_WND_CLASS](http://msdn.microsoft.com/library/55247a72-fb9e-4bde-87f3-747c08076971), le [DECLARE_WND_CLASS_EX](http://msdn.microsoft.com/library/0672c144-f2aa-4f6a-ae16-566e3a1f5411) ou [DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd). ATL construira un nom lors de la classe de fenêtre est enregistrée.  
  
##  <a name="a-namemwca--cwndclassinfomwc"></a><a name="m_wc"></a>CWndClassInfo::m_wc  
 Conserve les informations de classe de fenêtre dans un [WNDCLASSEX](http://msdn.microsoft.com/library/windows/desktop/ms633577) structure.  
  
```
WNDCLASSEX m_wc;
```  
  
### <a name="remarks"></a>Remarques  
 Si vous avez spécifié le [DECLARE_WND_CLASS](http://msdn.microsoft.com/library/55247a72-fb9e-4bde-87f3-747c08076971) (la valeur par défaut dans [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) ou [DECLARE_WND_CLASS_EX](http://msdn.microsoft.com/library/0672c144-f2aa-4f6a-ae16-566e3a1f5411) macro, `m_wc` contient des informations sur une nouvelle classe de fenêtre.  
  
 Si vous avez spécifié le [DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd) macro, `m_wc` contient des informations sur une superclasse, une classe de fenêtre qui est basée sur une classe existante mais utilise une autre procédure de fenêtre. [m_lpszOrigName](#m_lpszorigname) et [pWndProc](#pwndproc) enregistrer de nom de la classe de fenêtre existante et la procédure de fenêtre, respectivement.  
  
##  <a name="a-namepwndproca--cwndclassinfopwndproc"></a><a name="pwndproc"></a>CWndClassInfo::pWndProc  
 Pointe vers la procédure de fenêtre d’une classe de fenêtre existante.  
  
```
WNDPROC pWndProc;
```  
  
### <a name="remarks"></a>Notes  
 `CWndClassInfo`utilise `pWndProc` uniquement lorsque vous incluez le [DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd) macro dans votre définition de classe. Dans ce cas, `CWndClassInfo` enregistre une classe de fenêtre qui est basée sur une classe existante mais utilise une autre procédure de fenêtre. Procédure de fenêtre de la classe de fenêtre existante est enregistrée dans `pWndProc`. Pour plus d’informations, consultez la [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) vue d’ensemble.  
  
##  <a name="a-nameregistera--cwndclassinforegister"></a><a name="register"></a>CWndClassInfo::Register  
 Appelé par [CWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create) pour inscrire la classe de fenêtre si elle n’a pas encore été enregistré.  
  
```
ATOM Register(WNDPROC* pProc);
```  
  
### <a name="parameters"></a>Paramètres  
 `pProc`  
 [out] Indique la procédure de fenêtre d’origine d’une classe de fenêtre existante.  
  
### <a name="return-value"></a>Valeur de retour  
 Si l’opération réussit, un atome qui identifie la classe de fenêtre en cours d’inscription. Sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Si vous avez spécifié le [DECLARE_WND_CLASS](http://msdn.microsoft.com/library/55247a72-fb9e-4bde-87f3-747c08076971) (la valeur par défaut dans [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) ou [DECLARE_WND_CLASS_EX](http://msdn.microsoft.com/library/0672c144-f2aa-4f6a-ae16-566e3a1f5411) macro `Register` enregistre une nouvelle classe de fenêtre. Dans ce cas, le `pProc` paramètre n’est pas utilisé.  
  
 Si vous avez spécifié le [DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd) macro `Register` enregistre une superclasse, une classe de fenêtre qui est basée sur une classe existante mais utilise une autre procédure de fenêtre. Procédure de fenêtre de la classe de fenêtre existante est retournée dans `pProc`.  
  
## <a name="see-also"></a>Voir aussi  
 [CComControl (classe)](../../atl/reference/ccomcontrol-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)
