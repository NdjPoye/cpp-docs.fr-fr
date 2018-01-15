---
title: Nccalcsize_params, Structure | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: NCCALCSIZE_PARAMS
dev_langs: C++
helpviewer_keywords: NCCALCSIZE_PARAMS structure [MFC]
ms.assetid: 3424cd9f-806a-4089-82fb-414187589edf
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 76a0a16ff0a2c90c6dd6060badc2c79dde1af231
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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
 Spécifie un tableau de rectangles. La première ligne contient les nouvelles coordonnées d’une fenêtre qui a été déplacé ou redimensionné. Le deuxième contient les coordonnées de la fenêtre avant qu’il a été déplacé ou redimensionné. La troisième contient les coordonnées de la zone cliente d’une fenêtre avant qu’il a été déplacé ou redimensionné. Si la fenêtre est une fenêtre enfant, les coordonnées sont relatives à la zone cliente de la fenêtre parente. Si la fenêtre est une fenêtre de niveau supérieur, les coordonnées sont par rapport à l’écran.  
  
 *lppos*  
 Pointe vers un [WINDOWPOS](../../mfc/reference/windowpos-structure1.md) structure qui contient les valeurs de taille et la position spécifiées dans l’opération qui a provoqué la fenêtre d’être déplacé ou redimensionné.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** winuser.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)

