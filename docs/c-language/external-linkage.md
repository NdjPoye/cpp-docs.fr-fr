---
title: "Liaison externe | Microsoft Docs"
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
  - "liaison externe"
  - "liaison externe, à propos de la liaison externe"
  - "liaison (C++), externes"
ms.assetid: a6f8ea69-b405-4cdd-bf12-ad5462b73183
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Liaison externe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si la première déclaration au niveau de la portée du fichier d'un identificateur n'utilise pas le spécificateur de classe de stockage **static**, l'objet a une liaison externe.  
  
 Si la déclaration d'un identificateur pour une fonction ne comporte aucun *storage\-class\-specifier*, sa liaison est déterminée exactement comme s'il était déclaré avec le *storage\-class\-specifier*`extern`.  Si la déclaration d'un identificateur pour un objet a une portée de fichier et aucun *storage\-class\-specifier*, sa liaison est externe.  
  
 Le nom d'un identificateur avec liaison externe désigne la même fonction ou le même objet de données que toute autre déclaration du même nom avec liaison externe.  Les deux déclarations peuvent se trouver dans la même unité de traduction ou dans des unités différentes.  Si l'objet ou la fonction a également une durée de vie globale, il ou elle est partagé\(e\) par le programme entier.  
  
## Voir aussi  
 [Utilisation d'extern pour spécifier la liaison](../cpp/using-extern-to-specify-linkage.md)