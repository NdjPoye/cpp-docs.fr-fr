---
title: WINDOWPLACEMENT (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- WINDOWPLACEMENT
dev_langs:
- C++
helpviewer_keywords:
- WINDOWPLACEMENT structure
ms.assetid: ea7d61f6-eb57-478e-9b08-7c1d07091aa8
caps.latest.revision: 11
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
ms.openlocfilehash: 62cf7003f43d50d5998dd527ae5ad7b10ab95686
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="windowplacement-structure"></a>WINDOWPLACEMENT, structure
Le `WINDOWPLACEMENT` structure contient des informations relatives à l’emplacement d’une fenêtre sur l’écran**.**  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef struct tagWINDOWPLACEMENT {     /* wndpl */  
    UINT length;  
    UINT flags;  
    UINT showCmd;  
    POINT ptMinPosition;  
    POINT ptMaxPosition;  
    RECT rcNormalPosition;  
} WINDOWPLACEMENT;  
```  
  
#### <a name="parameters"></a>Paramètres  
 *length*  
 Spécifie la longueur, en octets, de la structure**.**  
  
 `flags`  
 Spécifie des indicateurs qui contrôlent la position de la fenêtre réduite et la méthode par laquelle la fenêtre est restaurée. Ce membre peut être une ou les deux des indicateurs suivants :  
  
- **WPF_SETMINPOSITION** Spécifie que les positions x et y de la fenêtre réduite peut être spécifiée**.** Cet indicateur doit être spécifiée si les coordonnées sont définies dans le **ptMinPosition** membre.  
  
- **WPF_RESTORETOMAXIMIZED** Spécifie que la fenêtre restaurée sera agrandie, indépendamment de si elle a été agrandie avant qu’il a été réduit. Ce paramètre est valid uniquement la prochaine fois que la fenêtre est restaurée. Il ne modifie pas le comportement de restauration par défaut. Cet indicateur est valide uniquement lorsque la **SW_SHOWMINIMIZED** valeur est spécifiée pour le **showCmd** membre.  
  
 *showCmd*  
 Spécifie l’état affiché en cours de la fenêtre. Ce membre peut être une des valeurs suivantes :  
  
- **SW_HIDE** masque la fenêtre et Active une autre fenêtre.  
  
- **SW_MINIMIZE** réduit la fenêtre spécifiée et Active la fenêtre de niveau supérieur dans la liste du système.  
  
- **SW_RESTORE** active et affiche une fenêtre. Si la fenêtre est réduite ou agrandie, Windows le restaure à sa taille et sa position d’origine (même en tant que **SW_SHOWNORMAL**).  
  
- **SW_SHOW** Active une fenêtre et l’affiche dans sa taille actuelle et son emplacement.  
  
- **SW_SHOWMAXIMIZED** Active une fenêtre et l’affiche comme une fenêtre agrandie.  
  
- **SW_SHOWMINIMIZED** Active une fenêtre et l’affiche sous forme d’icône.  
  
- **SW_SHOWMINNOACTIVE** affiche une fenêtre sous forme d’icône. La fenêtre actuellement active reste active.  
  
- **SW_SHOWNA** affiche une fenêtre dans son état actuel. La fenêtre actuellement active reste active.  
  
- **SW_SHOWNOACTIVATE** affiche une fenêtre dans sa taille et la position la plus récente. La fenêtre actuellement active reste active.  
  
- **SW_SHOWNORMAL** active et affiche une fenêtre. Si la fenêtre est réduite ou agrandie, Windows le restaure à sa taille et sa position d’origine (même en tant que **SW_RESTORE**).  
  
 *ptMinPosition*  
 Spécifie la position du coin supérieur gauche de la fenêtre lorsque la fenêtre est réduite.  
  
 `ptMaxPosition`  
 Spécifie la position du coin supérieur gauche de la fenêtre lorsque la fenêtre est agrandie.  
  
 *rcNormalPosition*  
 Spécifie les coordonnées de la fenêtre lorsque la fenêtre est en position normale (restaurée).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** winuser.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::SetWindowPlacement](../../mfc/reference/cwnd-class.md#setwindowplacement)


