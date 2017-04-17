---
title: POINT Structure1 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- POINT
- LPPOINT
dev_langs:
- C++
helpviewer_keywords:
- LPPOINT structure
- POINT structure
ms.assetid: 965736d8-4e53-41b6-9b8b-6961992dd21f
caps.latest.revision: 13
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
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: d1e2bb05f9bad785b13e79413866d8e0ce1e1faa
ms.lasthandoff: 02/24/2017

---
# <a name="point-structure1"></a>POINT de Structure1
Le **POINT** structure définit x* - * coordonnées d’un point.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef struct tagPOINT {  
    LONG x;  
    LONG y;  
} POINT;  
```  
  
#### <a name="parameters"></a>Paramètres  
 *x*  
 Spécifie la coordonnée x d’un point.  
  
 *y*  
 Spécifie la coordonnée y d’un point.  
  
## <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_Utilities&#37;](../../mfc/codesnippet/cpp/point-structure1_1.cpp)]  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** windef.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPoint (classe)](../../atl-mfc-shared/reference/cpoint-class.md)
