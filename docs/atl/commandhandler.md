---
title: CommandHandler | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CommandHandler
dev_langs:
- C++
helpviewer_keywords:
- CommandHandler function
ms.assetid: 662bc7bf-4a10-42b3-986d-d8bae4f63551
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2750f1e089ce5b6b3ef34325276a508ea0b80ddb
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="commandhandler"></a>CommandHandler
`CommandHandler` est la fonction identifiée par le troisième paramètre de la `COMMAND_HANDLER` macro dans votre table des messages.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
 
    LRESULT 
    CommandHandler 
 (
    WORD wNotifyCode,  
    WORD wID,  
    HWND hWndCtl,  
    BOOL& bHandled);
```  
  
#### <a name="parameters"></a>Paramètres  
 `wNotifyCode`  
 Le code de notification.  
  
 *wID*  
 Identificateur de l’élément de menu, le contrôle ou l’accélérateur.  
  
 *hWndCtl*  
 Handle vers un contrôle de fenêtre.  
  
 `bHandled`  
 Les jeux de mappage de message `bHandled` à **TRUE** avant `CommandHandler` est appelée. Si `CommandHandler` ne gère pas entièrement le message, il doit définir `bHandled` à **FALSE** pour indiquer le message nécessite un traitement supplémentaire.  
  
## <a name="return-value"></a>Valeur de retour  
 Le résultat du traitement du message. 0 en cas de réussite.  
  
## <a name="remarks"></a>Notes  
 Pour obtenir un exemple d’utilisation de ce gestionnaire de messages dans une table des messages, consultez [COMMAND_HANDLER](reference/message-map-macros-atl.md#command_handler).  
  
## <a name="see-also"></a>Voir aussi  
 [Implémentation d’une fenêtre](../atl/implementing-a-window.md)   
 [Tables des messages](../atl/message-maps-atl.md)   
 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)

