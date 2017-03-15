---
title: "Can I Reuse a Host Window? | Microsoft Docs"
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
  - "host windows"
ms.assetid: bcd08ab1-cfcf-49e3-b4e8-ac134d141005
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Can I Reuse a Host Window?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Il n'est pas recommandé réutilisiez les fenêtres hôte.  Pour garantir la robustesse de votre code, vous devez lier la durée de vie de la fenêtre hôte à la durée de vie d'un contrôle unique.  
  
## Voir aussi  
 [FAQ sur la relation contenant\-contenu des contrôles](../atl/atl-control-containment-faq.md)