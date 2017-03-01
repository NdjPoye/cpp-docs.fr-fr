---
title: NCCALCSIZE_PARAMS (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- NCCALCSIZE_PARAMS
dev_langs:
- C++
helpviewer_keywords:
- NCCALCSIZE_PARAMS structure
ms.assetid: 3424cd9f-806a-4089-82fb-414187589edf
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 88c25fd5e5862d5f0954ae853442c66eaf7320c8
ms.lasthandoff: 02/24/2017

---
# <a name="nccalcsizeparams-structure"></a>NCCALCSIZE_PARAMS, structure
Le `NCCALCSIZE_PARAMS` structure contient des informations qu’une application peut utiliser lors du traitement de la `WM_NCCALCSIZE` pour calculer la taille, la position et le contenu valid de la zone cliente d’une fenêtre de message.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef struct tagNCCALCSIZE_PARAMS {  
    RECT rgrc[3];  
    PWINDOWPOS lppos;  
} NCCALCSIZE_PARAMS;  
```  
  
#### <a name="parameters"></a>Paramètres  
 *rgrc*  
 Spécifie un tableau de rectangles. Le premier contient les nouvelles coordonnées d’une fenêtre qui a été déplacé ou redimensionné. Le second contient les coordonnées de la fenêtre avant qu’il a été déplacé ou redimensionné. La troisième contient les coordonnées de la zone cliente d’une fenêtre avant qu’il a été déplacé ou redimensionné. Si la fenêtre est une fenêtre enfant, les coordonnées sont relatives à la zone client de la fenêtre parente. Si la fenêtre est une fenêtre de niveau supérieur, les coordonnées sont par rapport à l’écran.  
  
 *lppos*  
 Pointe vers une [WINDOWPOS](../../mfc/reference/windowpos-structure1.md) structure qui contient les valeurs de taille et la position spécifiées dans l’opération qui a provoqué la fenêtre d’être déplacé ou redimensionné.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** winuser.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)


