---
title: POINT Structure1 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- POINT
- LPPOINT
dev_langs: C++
helpviewer_keywords:
- LPPOINT structure [MFC]
- POINT structure [MFC]
ms.assetid: 965736d8-4e53-41b6-9b8b-6961992dd21f
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5744ade39403248daed02c23efc8f01ee94ec4ec
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="point-structure1"></a>POINT de Structure1
Le **POINT** structure définit x *-*  coordonnées d’un point.  
  
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
 [!code-cpp[NVC_MFC_Utilities#37](../../mfc/codesnippet/cpp/point-structure1_1.cpp)]  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** windef.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPoint, classe](../../atl-mfc-shared/reference/cpoint-class.md)