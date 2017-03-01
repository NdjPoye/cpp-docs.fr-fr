---
title: Structure PAINTSTRUCT | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- PAINTSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- PAINTSTRUCT structure
ms.assetid: 81ce4993-3e89-43b2-8c98-7946f1314d24
caps.latest.revision: 12
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 07b79b9ae20bd6e5648c67fa277ddde2929028c7
ms.lasthandoff: 02/24/2017

---
# <a name="paintstruct-structure"></a>PAINTSTRUCT, structure
Le `PAINTSTRUCT` structure contient des informations qui peuvent être utilisées pour peindre la zone cliente d’une fenêtre.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef struct tagPAINTSTRUCT {  
    HDC hdc;  
    BOOL fErase;  
    RECT rcPaint;  
    BOOL fRestore;  
    BOOL fIncUpdate;  
    BYTE rgbReserved[16];  
} PAINTSTRUCT;  
```  
  
#### <a name="parameters"></a>Paramètres  
 *HDC*  
 Identifie le contexte d’affichage à utiliser pour peindre.  
  
 *fErase*  
 Spécifie si l’arrière-plan doit être redessiné. Il n’est pas 0 si l’application doit redessiner l’arrière-plan. L’application est responsable du dessin de l’arrière-plan si une classe de fenêtre Windows est créée sans un pinceau d’arrière-plan (voir la description de la **hbrBackground** membre de la [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]).  
  
 *rcPaint*  
 Spécifie l’angle supérieur gauche et inférieure droite du rectangle dans lequel le dessin est demandé.  
  
 *fRestore*  
 Membre réservé. Il est utilisé en interne par Windows.  
  
 *fIncUpdate*  
 Membre réservé. Il est utilisé en interne par Windows.  
  
 *rgbReserved [16]*  
 Membre réservé. Un bloc réservé de la mémoire utilisée en interne par Windows.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** winuser.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPaintDC::m_ps](../../mfc/reference/cpaintdc-class.md#m_ps)


