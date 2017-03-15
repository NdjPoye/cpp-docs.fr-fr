---
title: "Liaison interne | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "liaison interne"
  - "liaison (C++), interne"
ms.assetid: 80be7b51-c930-43db-94d6-4f09a64077bf
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Liaison interne
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si la déclaration d'un identificateur de portée de fichier pour un objet ou une fonction contient le *storage\-class\-specifier* **static**, l'identificateur a une liaison interne.  Sinon, l'identificateur a une liaison externe.  Consultez [Classes de stockage](../c-language/c-storage-classes.md) pour plus d'informations sur l'élément non terminal *storage\-class\-specifier*.  
  
 Dans une unité de traduction, chaque instance d'un identificateur avec une liaison interne désigne le même identificateur ou la même fonction.  Les identificateurs liés en interne sont spécifiques à une unité de traduction.  
  
## Voir aussi  
 [Utilisation d'extern pour spécifier la liaison](../cpp/using-extern-to-specify-linkage.md)