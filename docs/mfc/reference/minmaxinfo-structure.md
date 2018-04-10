---
title: Minmaxinfo, Structure | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- MINMAXINFO
dev_langs:
- C++
helpviewer_keywords:
- MINMAXINFO structure [MFC]
ms.assetid: be6fb578-f98a-4581-9ada-be9df308ed2f
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c2c799299ef9058648d6b056dcd02fe580f06148
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="minmaxinfo-structure"></a>MINMAXINFO, structure
Le `MINMAXINFO` structure contient des informations sur la taille agrandie d’une fenêtre et position et sa taille minimale et maximale de suivi.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef struct tagMINMAXINFO {  
    POINT ptReserved;  
    POINT ptMaxSize;  
    POINT ptMaxPosition;  
    POINT ptMinTrackSize;  
    POINT ptMaxTrackSize;  
} MINMAXINFO;  
```  
  
#### <a name="parameters"></a>Paramètres  
 *ptReserved*  
 Réservé à un usage interne.  
  
 *ptMaxSize*  
 Spécifie la largeur agrandie (point.x) et la hauteur agrandie (point.y) de la fenêtre.  
  
 `ptMaxPosition`  
 Spécifie la position du côté gauche de la fenêtre agrandie (point.x) et la position du bord supérieur de la fenêtre agrandie (point.y).  
  
 *ptMinTrackSize*  
 Spécifie la largeur (point.x) de suivi minimale et la hauteur (point.y) de la fenêtre de suivi minimale.  
  
 *ptMaxTrackSize*  
 Spécifie le nombre maximal (point.x) de largeur de suivi et la valeur maximale (point.y) de hauteur de la fenêtre de suivi.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** winuser.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)

