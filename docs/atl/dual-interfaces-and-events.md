---
title: "Interfaces doubles et événements | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- events [C++], dual interfaces
- dual interfaces, events
ms.assetid: bb382f7c-e885-4274-bf07-83f3602615d2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 87774f0237eb42c4bd2f97185230b3c869688ca8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="dual-interfaces-and-events"></a>Interfaces doubles et événements
Bien qu’il soit possible de concevoir une interface d’événement comme un double, il existe de nombreuses raisons d’une bonne conception ne pas à le faire. La raison fondamentale est que la source de l’événement se déclenche uniquement l’événement via la vtable ou `Invoke`, mais pas les deux. Si la source d’événement déclenche l’événement comme un appel de méthode vtable direct, le `IDispatch` méthodes ne seront jamais utilisées et il est clair que l’interface doit être une interface vtable pure. Si la source d’événement déclenche l’événement comme un appel à `Invoke`, les méthodes vtable ne seront jamais utilisées et il est clair que l’interface doit être une dispinterface. Si vous définissez vos interfaces d’événements comme duals, vous devez exiger que les clients implémentent une partie d’une interface qui ne sera jamais utilisée.  
  
> [!NOTE]
>  Cet argument ne s’applique pas aux interfaces doubles, en général. Du point de vue de l’implémentation, les interfaces doubles sont un moyen rapide et pratique bien pris en charge d’implémenter des interfaces qui sont accessibles à un large éventail de clients.  
  
 Il existe d’autres raisons pour éviter les interfaces d’événements doubles ; Visual Basic ni Internet Explorer ne les prennent en charge.  
  
## <a name="see-also"></a>Voir aussi  
 [Interfaces doubles et ATL](../atl/dual-interfaces-and-atl.md)

