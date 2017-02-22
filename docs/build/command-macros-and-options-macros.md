---
title: "Macros de commandes et macros d&#39;options | Microsoft Docs"
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
  - "macros de commande dans NMAKE"
  - "macros, macros de commande"
  - "macros, macros d'options"
  - "macros d'options"
ms.assetid: 50dff03c-0dc3-4a8a-9a17-57e0e4ea9bac
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Macros de commandes et macros d&#39;options
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les macros de commandes sont prédéfinies pour des produits Microsoft.  Les macros des options représentent des options de ces produits et sont non définies par défaut.  Les deux types sont utilisés dans les règles d'inférence prédéfinies et peuvent être employés dans des blocs de description ou des règles d'inférence définies par l'utilisateur.  Les macros de commandes peuvent être redéfinies pour représenter tout ou partie d'une ligne de commande, notamment les options.  Les macros d'options génèrent une chaîne nulle si elles ne sont pas définies.  
  
|Produit Microsoft|Macro de commande|Définie comme|Macro d'options|  
|-----------------------|-----------------------|-------------------|---------------------|  
|Macro\-assembleur|**As**|ml|**AFLAGS**|  
|Compilateur Basic|**BC**|bc|**BFLAGS**|  
|Compilateur C|**CC**|cl|**CFLAGS**|  
|Compilateur C\+\+|**CPP**|cl|**CPPFLAGS**|  
|Compilateur C\+\+|**CXX**|cl|**CXXFLAGS**|  
|Compilateur de ressources|**RC**|rc|**RFLAGS**|  
  
## Voir aussi  
 [Macros spéciales de NMAKE](../build/special-nmake-macros.md)