---
title: "Dual Interfaces and Events | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "interfaces doubles, événements"
  - "événements (C++), interfaces doubles"
ms.assetid: bb382f7c-e885-4274-bf07-83f3602615d2
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Dual Interfaces and Events
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pendant qu'il est possible de concevoir une interface d'événement comme double, un certain nombre de bonnes raisons de conception de ne pas faire.  La raison fondamentale est que la source de l'événement déclenche uniquement l'événement via le pointeur vtable ou via `Invoke`, pas les deux.  Si la source d'événement déclenche l'événement comme un appel de méthode vtable direct, les méthodes d' `IDispatch` ne seront jamais utilisées et il est clair que l'interface doit avoir été une interface vtable pure.  Si la source d'événement déclenche l'événement comme un appel à `Invoke`, les méthodes vtable ne seront jamais utilisées et il est clair que l'interface doit avoir été une dispinterface.  Si vous définissez les interfaces d'événement comme conjugue, vous exigerez les clients d'implémenter une partie d'une interface qui ne sera jamais utilisée.  
  
> [!NOTE]
>  Cet argument ne s'applique pas aux interfaces doubles, en général.  Du point de vue d'implémentation, conjugue sont un moyen rapide, pratique, et bien\- prise en charge d'implémenter les interfaces qui sont accessibles à une large gamme de clients.  
  
 Il existe d'autres raisons d'éviter de doublons interfaces d'événement ; ni Visual Basic ou Internet Explorer ne les prennent en charge.  
  
## Voir aussi  
 [Dual Interfaces and ATL](../atl/dual-interfaces-and-atl.md)