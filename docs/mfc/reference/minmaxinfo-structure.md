---
title: MINMAXINFO (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MINMAXINFO
dev_langs:
- C++
helpviewer_keywords:
- MINMAXINFO structure
ms.assetid: be6fb578-f98a-4581-9ada-be9df308ed2f
caps.latest.revision: 10
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
ms.openlocfilehash: 772416bdac3c72f55644fa31aef23ba76a14e606
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

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
 Spécifie la largeur (point.x) de suivi minimale et hauteur (point.y) de la fenêtre de suivi minimale.  
  
 *ptMaxTrackSize*  
 Spécifie le nombre maximal de suivi largeur (point.x) et une hauteur (point.y) de la fenêtre de suivi.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** winuser.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)


