---
title: "Macros de classe de fenêtre | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: ce18681a-2bab-4453-9895-0f3ea47c2b24
caps.latest.revision: 16
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
ms.sourcegitcommit: 8cdedc5cfac9d49df812ae6fcfcc548201b1edb5
ms.openlocfilehash: f32926b6efd4ffb9c0541c0574a479c13dac01df
ms.lasthandoff: 02/24/2017

---
# <a name="window-class-macros"></a>Macros de classe de fenêtre
Ces macros définissent des utilitaires de classe de fenêtre.  
  
|||  
|-|-|  
|[DECLARE_WND_CLASS](#declare_wnd_class)|Vous permet de spécifier le nom d’une nouvelle classe de fenêtre.| 
|[DECLARE_WND_CLASS2](#declare_wnd_class2)|(Visual Studio 2017) Vous permet de spécifier le nom d’une nouvelle classe et la classe englobante dont procédure de fenêtre utilise la nouvelle classe.| 
|[DECLARE_WND_SUPERCLASS](#declare_wnd_superclass)|Vous permet de spécifier le nom d’une classe de fenêtre existante sur laquelle une nouvelle classe de fenêtre doit être basée.|  
|[DECLARE_WND_CLASS_EX](#declare_wnd_class_ex)|Vous permet de spécifier les paramètres d’une classe.|  

## <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h  
   
##  <a name="a-namedeclarewndclassa--declarewndclass"></a><a name="declare_wnd_class"></a>DECLARE_WND_CLASS  
 Vous permet de spécifier le nom d’une nouvelle classe de fenêtre. Placez cette macro dans la classe de contrôle d’un contrôle ActiveX ATL.  
  
```
DECLARE_WND_CLASS( WndClassName )
```  
  
### <a name="parameters"></a>Paramètres  
 `WndClassName`  
 [in] Le nom de la nouvelle classe de fenêtre. Si **NULL**, ATL générera un nom de classe de fenêtre.  
  
### <a name="remarks"></a>Remarques  
 Si vous utilisez l’option /permissive-compiler, DECLARE_WND_CLASS provoquera une erreur du compilateur ; Utilisez plutôt DECLARE_WND_CLASS2.
 
 DECLARE_WND_CLASS vous permet de spécifier le nom d’une nouvelle classe dont les informations seront gérées par [CWndClassInfo](cwndclassinfo-class.md). `DECLARE_WND_CLASS`définit la nouvelle classe de fenêtre en implémentant la fonction statique suivante :  
  
 [!code-cpp[127 NVC_ATL_Windowing](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]  
  
 `DECLARE_WND_CLASS`Spécifie les styles suivants pour la nouvelle fenêtre :  
  
-   CS_HREDRAW  
  
-   CS_VREDRAW  
  
-   CS_DBLCLKS  
  
 `DECLARE_WND_CLASS`Spécifie également la couleur d’arrière-plan de la fenêtre par défaut. Utilisez le [DECLARE_WND_CLASS_EX](#declare_wnd_class_ex) macro pour fournir vos propres styles et la couleur d’arrière-plan.  
  
 [CWindowImpl](cwindowimpl-class.md) utilise le `DECLARE_WND_CLASS` macro pour créer une fenêtre basée sur une nouvelle classe de fenêtre. Pour remplacer ce comportement, utilisez la [DECLARE_WND_SUPERCLASS](#declare_wnd_superclass) (macro), ou fournir votre propre implémentation de la [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo) (fonction).  

  
 Pour plus d’informations sur l’utilisation des fenêtres dans ATL, consultez l’article [Classes de fenêtre ATL](../../atl/atl-window-classes.md).  

##  <a name="a-namedeclarewndclass2a--declarewndclass2"></a><a name="declare_wnd_class2"></a>DECLARE_WND_CLASS2  
 (Visual Studio 2017) Similaire à DECLARE_WND_CLASS, mais avec un paramètre supplémentaire qui permet d’éviter une erreur de nom dépendant lors de la compilation avec le /permissive-option.
  
```
DECLARE_WND_CLASS2( WndClassName, EnclosingClass )
```  
  
### <a name="parameters"></a>Paramètres  
 `WndClassName`  
 [in] Le nom de la nouvelle classe de fenêtre. Si **NULL**, ATL générera un nom de classe de fenêtre. 

 `EnclosingClass`  
 [in] Le nom de la classe de fenêtre qui contient la nouvelle classe de fenêtre. Ne peut pas être **NULL**.  
  
### <a name="remarks"></a>Notes 
Si vous utilisez la /permissive-option, DECLARE_WND_CLASS entraîne une erreur de compilation, car elle contient un nom dépendant. DECLARE_WND_CLASS2, vous devez nommer explicitement la classe que cette macro est utilisée dans et n’entraîne pas l’erreur sous la /permissive-flag.
Sinon, cette macro est identique à [DECLARE_WND_CLASS](#declare_wnd_class).
   
##  <a name="a-namedeclarewndsuperclassa--declarewndsuperclass"></a><a name="declare_wnd_superclass"></a>DECLARE_WND_SUPERCLASS  
 Vous permet de spécifier les paramètres d’une classe. Placez cette macro dans la classe de contrôle d’un contrôle ActiveX ATL.  
  
```
DECLARE_WND_SUPERCLASS( WndClassName, OrigWndClassName )
```  
  
### <a name="parameters"></a>Paramètres  
 `WndClassName`  
 [in] Le nom de la fenêtre classe celle-ci sera `OrigWndClassName`. Si **NULL**, ATL générera un nom de classe de fenêtre.  
  
 `OrigWndClassName`  
 [in] Le nom d’une classe de fenêtre existante.  
  
### <a name="remarks"></a>Remarques  
 Cette macro vous permet de spécifier le nom d’une classe de fenêtre qui sera surclasser une classe de fenêtre. [CWndClassInfo](cwndclassinfo-class.md) gère les informations de la superclasse.  
  
 `DECLARE_WND_SUPERCLASS`implémente la fonction statique suivante :  
  
 [!code-cpp[127 NVC_ATL_Windowing](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]  
  
 Par défaut, [CWindowImpl](cwindowimpl-class.md) utilise le [DECLARE_WND_CLASS](#declare_wnd_class) macro pour créer une fenêtre basée sur une nouvelle classe de fenêtre. En spécifiant le `DECLARE_WND_SUPERCLASS` macro dans un `CWindowImpl`-classe dérivée, la classe de fenêtre est basée sur une classe existante mais utilisera votre procédure de fenêtre. Cette technique est appelée surclasser.  
  
 Outre l’utilisation de la `DECLARE_WND_CLASS` et `DECLARE_WND_SUPERCLASS` macros, vous pouvez remplacer le [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo) fonction avec votre propre implémentation.  

  
 Pour plus d’informations sur l’utilisation des fenêtres dans ATL, consultez l’article [Classes de fenêtre ATL](../../atl/atl-window-classes.md).  
  
##  <a name="a-namedeclarewndclassexa--declarewndclassex"></a><a name="declare_wnd_class_ex"></a>DECLARE_WND_CLASS_EX  
 Vous permet de spécifier le nom d’une classe de fenêtre existante sur laquelle une nouvelle classe de fenêtre doit être basée. Placez cette macro dans la classe de contrôle d’un contrôle ActiveX ATL.  
  
```
DECLARE_WND_CLASS_EX( WndClassName, style, bkgnd )
```  
  
### <a name="parameters"></a>Paramètres  
 `WndClassName`  
 [in] Le nom de la nouvelle classe de fenêtre. Si **NULL**, ATL générera un nom de classe de fenêtre.  
  
 `style`  
 [in] Le style de la fenêtre.  
  
 *arrière-plan*  
 [in] La couleur d’arrière-plan de la fenêtre.  
  
### <a name="remarks"></a>Remarques  
 Cette macro vous permet de spécifier les paramètres de classe d’une nouvelle classe de fenêtre, dont les informations seront gérées par [CWndClassInfo](cwndclassinfo-class.md). `DECLARE_WND_CLASS_EX`définit la nouvelle classe de fenêtre en implémentant la fonction statique suivante :  
  
 [!code-cpp[127 NVC_ATL_Windowing](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]  
  
 Si vous souhaitez utiliser les styles par défaut et la couleur d’arrière-plan, utilisez la [DECLARE_WND_CLASS](#declare_wnd_class) macro. Pour plus d’informations sur l’utilisation des fenêtres dans ATL, consultez l’article [Classes de fenêtre ATL](../../atl/atl-window-classes.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Macros](atl-macros.md)









