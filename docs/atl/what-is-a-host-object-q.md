---
title: "What Is a Host Object? | Microsoft Docs"
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
  - "host objects"
ms.assetid: 4f8da992-b27e-45e8-b5e0-c8b1dcae4fac
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# What Is a Host Object?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un objet hôte est un objet COM qui représente le conteneur de contrôles ActiveX fourni par ATL pour une fenêtre spécifique.  Les sous\-classes d'objets hôtes la fenêtre de conteneur afin qu'il puisse refléter des messages au contrôle, il fournit des interfaces nécessaires de conteneur à utiliser par le contrôle, et il expose les interfaces d' [IAxWinHostWindow](../atl/reference/iaxwinhostwindow-interface.md) et d' [IAxWinAmbientDispatch](../atl/reference/iaxwinambientdispatch-interface.md) pour vous permettre de configurer l'environnement du contrôle.  
  
 Vous pouvez utiliser l'objet hôte pour définir les propriétés ambiantes du conteneur.  
  
## Voir aussi  
 [FAQ sur la relation contenant\-contenu des contrôles](../atl/atl-control-containment-faq.md)