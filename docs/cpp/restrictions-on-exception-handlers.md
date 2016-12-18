---
title: "Restrictions sur les gestionnaires d&#39;exceptions | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gestion des exceptions, gestionnaires d'exceptions"
  - "restrictions, gestionnaires d'exceptions"
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Restrictions sur les gestionnaires d&#39;exceptions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La limitation principale concernant l'utilisation des gestionnaires d'exceptions dans le code tient au fait que vous ne pouvez pas utiliser une instruction `goto` pour accéder à un bloc d'instruction `__try`.  À la place, vous devez entrer dans le bloc d'instruction via le flux de contrôle normal.  Vous pouvez effectuer un saut hors d'un bloc d'instruction `__try` et imbriquer des gestionnaires d'exceptions comme vous le souhaitez.  
  
## Voir aussi  
 [Écriture d'un gestionnaire d'exceptions](../cpp/writing-an-exception-handler.md)   
 [Gestion structurée des exceptions](../cpp/structured-exception-handling-c-cpp.md)