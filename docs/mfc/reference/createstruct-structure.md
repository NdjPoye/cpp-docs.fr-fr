---
title: CREATESTRUCT (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CREATESTRUCT
dev_langs:
- C++
helpviewer_keywords:
- CREATESTRUCT structure
ms.assetid: 028c7b5e-4fdc-48da-a550-d3e4f9e6cc85
caps.latest.revision: 14
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: ec72d4725cb7e5959369b24a6ff7f0e3e9da1ca7
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="createstruct-structure"></a>CREATESTRUCT, structure
Le `CREATESTRUCT` structure définit les paramètres d’initialisation passés à la procédure de fenêtre d’une application.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef struct tagCREATESTRUCT {  
    LPVOID lpCreateParams;  
    HANDLE hInstance;  
    HMENU hMenu;  
    HWND hwndParent;  
    int cy;  
    int cx;  
    int y;  
    int x;  
    LONG style;  
    LPCSTR lpszName;  
    LPCSTR lpszClass;  
    DWORD dwExStyle;  
} CREATESTRUCT;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `lpCreateParams`  
 Points de données à utiliser pour créer la fenêtre.  
  
 `hInstance`  
 Identifie le handle d’instance du module du module propriétaire de la nouvelle fenêtre.  
  
 `hMenu`  
 Identifie le menu pour être utilisé par la nouvelle fenêtre. Si une fenêtre enfant, contient l’ID d’entier.  
  
 `hwndParent`  
 Identifie la fenêtre propriétaire de la nouvelle fenêtre. Ce membre est **NULL** si la nouvelle fenêtre est une fenêtre de niveau supérieur.  
  
 `cy`  
 Spécifie la hauteur de la nouvelle fenêtre.  
  
 `cx`  
 Spécifie la largeur de la nouvelle fenêtre.  
  
 `y`  
 Spécifie la coordonnée y de l’angle supérieur gauche de la nouvelle fenêtre. Coordonnées sont relatives à la fenêtre parent si la nouvelle fenêtre est une fenêtre enfant ; dans le cas contraire coordonnées sont exprimées par rapport à l’origine de l’écran.  
  
 `x`  
 Spécifie la coordonnée x de l’angle supérieur gauche de la nouvelle fenêtre. Coordonnées sont relatives à la fenêtre parent si la nouvelle fenêtre est une fenêtre enfant ; dans le cas contraire coordonnées sont exprimées par rapport à l’origine de l’écran.  
  
 `style`  
 Spécifie la nouvelle fenêtre [style](../../mfc/reference/styles-used-by-mfc.md).  
  
 `lpszName`  
 Pointe vers une chaîne terminée par le caractère null qui spécifie le nom de la nouvelle fenêtre.  
  
 `lpszClass`  
 Pointe vers une chaîne terminée par le caractère null qui spécifie le nom de la classe de la nouvelle fenêtre Windows (un [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) structure ; pour plus d’informations, consultez le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]).  
  
 `dwExStyle`  
 Spécifie le [style étendu](../../mfc/reference/extended-window-styles.md) pour la nouvelle fenêtre.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** winuser.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate)



