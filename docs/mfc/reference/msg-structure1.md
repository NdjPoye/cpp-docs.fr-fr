---
title: MSG Structure1 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: MSG
dev_langs: C++
helpviewer_keywords: MSG structure [MFC]
ms.assetid: dc166d27-9423-41f1-9599-5ba76d2f0138
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b856ea17e4542bee68d55b22069e559592199939
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="msg-structure1"></a>MSG Structure1
Le `MSG` structure contient des informations de message à partir de la file d’attente des messages d’un thread.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef struct tagMSG {     // msg    
    HWND hwnd;  
    UINT message;  
    WPARAM wParam;  
    LPARAM lParam;  
    DWORD time;  
    POINT pt;  
} MSG;  
```  
  
#### <a name="parameters"></a>Paramètres  
 *HWND*  
 Identifie la fenêtre dont procédure de fenêtre reçoit le message.  
  
 `message`  
 Spécifie le numéro du message.  
  
 `wParam`  
 Spécifie des informations supplémentaires sur le message. La signification exacte dépend de la valeur de la **message** membre.  
  
 `lParam`  
 Spécifie des informations supplémentaires sur le message. La signification exacte dépend de la valeur de la **message** membre.  
  
 `time`  
 Spécifie l’heure à laquelle le message a été publié.  
  
 `pt`  
 Spécifie la position du curseur, en coordonnées d’écran, lorsque le message a été publié.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** winuser.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

