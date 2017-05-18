---
title: Tables (MFC) des messages | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.messages
dev_langs:
- C++
helpviewer_keywords:
- message maps [C++], MFC
- Windows messages [C++], message maps
- messages [C++], Windows
- MFC [C++], messages
ms.assetid: 3f9855e4-9d7d-4b64-8f3f-a19ea3cf79ba
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
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: bb31d35e221c9f5d06dc34408bed500b4a18b077
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="message-maps-mfc"></a>Tables des messages (MFC)
Cette section de la référence répertorie tous les [macros de mappage de message](../../mfc/reference/message-map-macros-mfc.md) et tous les [CWnd](../../mfc/reference/cwnd-class.md) des prototypes de fonction des entrées de table des messages, ainsi que le membre correspondant :  
  
|Catégorie|Description|  
|--------------|-----------------|  
|[Gestionnaire de messages WM_COMMAND](../../mfc/reference/wm-command-message-handler.md)|Gère les **WM_COMMAND** messages générés par les sélections de menu utilisateur ou les touches d’accès rapide.|  
|[Gestionnaires de messages de Notification de fenêtre enfant](../../mfc/reference/child-window-notification-message-handlers.md)|Gérer les messages de notification à partir des fenêtres enfants.|  
|[Gestionnaires de messages WM_](../../mfc/reference/handlers-for-wm-messages.md)|Gérer les **WM_** messages, tel que `WM_PAINT`.|  
|[Gestionnaires de messages définis par l’utilisateur](../../mfc/reference/user-defined-handlers.md)|Gérer les messages définis par l’utilisateur.|  
  
 (Pour obtenir une explication de la terminologie et les conventions utilisées dans ce guide de référence, consultez [comment utiliser le renvoi de mappage de Message](../../mfc/reference/how-to-use-the-message-map-cross-reference.md).)  
  
 Étant donné que Windows est un système d’exploitation orienté message, une grande partie de la programmation pour l’environnement Windows implique la gestion des messages. Chaque fois, cliquez sur un événement tel qu’une combinaison de touches ou de la souris se produit, un message est envoyé à l’application, qui doit ensuite gérer l’événement.  
  
 La bibliothèque Microsoft Foundation Class offre un modèle de programmation optimisé pour la programmation basée sur message. Dans ce modèle, « tables des messages » sont utilisés pour désigner les fonctions gérera différents messages pour une classe particulière. Tables des messages contiennent une ou plusieurs macros qui spécifient quels messages seront traités par les fonctions. Par exemple, une carte message contenant un `ON_COMMAND` macro pourrait ressembler à ceci :  
  
 [!code-cpp[NVC_MFCMessageMaps&#16;](../../mfc/reference/codesnippet/cpp/message-maps-mfc_1.cpp)]  
  
 Le `ON_COMMAND` macro est utilisée pour traiter les messages de commande générés par les menus, les boutons et les touches d’accès rapide. [Macros](../../mfc/reference/message-map-macros-mfc.md) sont disponibles pour mapper les éléments suivants :  
  
## <a name="windows-messages"></a>Messages Windows  
  
-   Notifications de contrôle  
  
-   Messages définis par l’utilisateur  
  
## <a name="command-messages"></a>Messages de commande  
  
-   Inscrit les messages définis par l’utilisateur  
  
-   Messages de mise à jour d’interface utilisateur  
  
## <a name="ranges-of-messages"></a>Plages de Messages  
  
-   Commandes  
  
-   Messages de gestionnaire de mise à jour  
  
-   Notifications de contrôle  
  
 Bien que les macros de table des messages importants, généralement n’avoir à les utiliser directement. Il s’agit, car la fenêtre Propriétés crée automatiquement des entrées de table des messages dans vos fichiers sources lorsque vous l’utilisez pour associer des fonctions de gestion des messages avec des messages. Chaque fois que vous souhaitez modifier ou ajouter une entrée de table des messages, vous pouvez utiliser la fenêtre Propriétés.  
  
> [!NOTE]
>  La fenêtre Propriétés ne prend pas en charge les plages de la table des messages. Vous devez écrire vous-même ces entrées de table des messages.  
  
 Toutefois, les tables des messages sont une partie importante de la bibliothèque Microsoft Foundation Class. Vous devez comprendre ce qu’elles font et documentation est fournie pour eux.  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)


