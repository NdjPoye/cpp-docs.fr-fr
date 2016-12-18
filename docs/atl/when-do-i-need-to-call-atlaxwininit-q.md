---
title: "When Do I Need to Call AtlAxWinInit? | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "AtlAxWinInit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AtlAxWinInit method"
ms.assetid: 080b9cfe-d85a-4439-a9e9-ab3966ebaa8e
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# When Do I Need to Call AtlAxWinInit?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[AtlAxWinInit](../Topic/AtlAxWinInit.md) stocke la classe de fenêtre de **"AtlAxWin80"** \(ainsi que des messages personnalisés de fenêtre\) afin que cette fonction doit être appelée avant d'essayer de créer une fenêtre hôte.  Toutefois, vous n'avez pas toujours besoin d'appeler cette fonction explicitement, comme les API d'hébergement \(et les classes qui utilisent\) appellent souvent cette fonction pour vous.  Il n'existe aucun mal en appelant cette fonction plusieurs fois.  Pour plus d'informations, consultez [Quel est l'API d'Hébergement contrôle ATL ?](../atl/what-is-the-atl-control-hosting-api-q.md).  
  
## Voir aussi  
 [When Do I Need to Call AtlAxWinTerm?](../atl/when-do-i-need-to-call-atlaxwinterm-q.md)   
 [FAQ sur la relation contenant\-contenu des contrôles](../atl/atl-control-containment-faq.md)