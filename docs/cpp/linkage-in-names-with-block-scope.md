---
title: "Liaison des noms avec la port&#233;e de bloc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "portée de bloc (C++)"
  - "liaison externe, règles de liaison de portée"
  - "liaison (C++), règles de liaison de portée"
  - "noms (C++), règles de liaison de portée"
  - "portée (C++), règles de liaison"
ms.assetid: 73efa91a-f761-47f7-bbd9-9f9e3508e218
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Liaison des noms avec la port&#233;e de bloc
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les règles de liaison suivantes s'appliquent aux noms avec une portée de bloc \(noms locaux\) :  
  
-   Les noms déclarés comme `extern` ont une liaison externe, sauf s'ils ont été préalablement déclarés comme **static**.  
  
-   Tous les autres noms avec portée de bloc ne possèdent pas de liaison.  
  
## Voir aussi  
 [Programme et liaison](../cpp/program-and-linkage-cpp.md)