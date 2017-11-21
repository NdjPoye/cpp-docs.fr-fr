---
title: RECT Structure1 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LPRECT
- RECT
dev_langs: C++
helpviewer_keywords:
- RECT structure [MFC]
- LPRECT structure [MFC]
ms.assetid: 1b3160de-64e9-40d1-89eb-af3e0fd6acf0
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9d3a33330ace97db19521362384356b58a6c8dca
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="rect-structure1"></a>RECT Structure1
Le `RECT` structure définit les coordonnées des angles supérieur gauche et à droite d’un rectangle.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef struct tagRECT {  
    LONG left;  
    LONG top;  
    LONG right;  
    LONG bottom;  
} RECT;  
```  
  
## <a name="members"></a>Membres  
 `left`  
 Spécifie la coordonnée x du coin supérieur gauche d’un rectangle.  
  
 `top`  
 Spécifie la coordonnée y du coin supérieur gauche d’un rectangle.  
  
 `right`  
 Spécifie la coordonnée x de l’angle inférieur droit d’un rectangle.  
  
 `bottom`  
 Spécifie la coordonnée y du coin inférieur droit d’un rectangle.  
  
## <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_Utilities#38](../../mfc/codesnippet/cpp/rect-structure1_1.cpp)]  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** windef.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRect, classe](../../atl-mfc-shared/reference/crect-class.md)
