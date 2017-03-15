---
title: "Can I Host More Than One Control in a Single Window? | Microsoft Docs"
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
  - "controls [ATL], hosting multiple"
  - "windows [C++], hosting multiple controls"
ms.assetid: 3a967a1a-7e7e-42e3-8eed-f7bde912363f
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Can I Host More Than One Control in a Single Window?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Il n'est pas possible d'héberger plusieurs contrôles dans une fenêtre unique d'hôte ATL.  Chaque fenêtre hôte est conçue pour contenir exactement un contrôle à la fois \(cela permet d'un mécanisme simple pour gérer des propriétés ambiantes de point d'arrêt de message et pour chaque contrôle\).  Toutefois, si vous avez besoin de l'utilisateur pour afficher plusieurs contrôles dans un guichet unique, il est chose facile de créer des fenêtres hôtes multiples comme enfants de cette fenêtre.  
  
## Voir aussi  
 [FAQ sur la relation contenant\-contenu des contrôles](../atl/atl-control-containment-faq.md)