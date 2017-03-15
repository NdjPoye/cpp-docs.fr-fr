---
title: "Tableaux dans les expressions | Microsoft Docs"
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
  - "tableaux (C++), dans des expressions"
  - "expressions (C++), tableaux dans"
ms.assetid: 6e5a795b-d6bd-4e39-b313-6a20d47c4d4b
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Tableaux dans les expressions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsqu'un identificateur de type tableau apparaît dans une expression autre que `sizeof`, address\-of \(**&**\) ou l'initialisation d'une référence, il est converti en pointeur vers le premier élément du tableau.  Par exemple :  
  
```  
char szError1[] = "Error: Disk drive not ready.";  
char *psz = szError1;  
```  
  
 Le pointeur `psz` pointe vers le premier élément du tableau `szError1`.  Notez que les tableaux, contrairement aux pointeurs, ne sont pas des valeurs lvalues modifiables.  Par conséquent, l'assignation suivante n'est pas conforme :  
  
```  
szError1 = psz;  
```  
  
## Voir aussi  
 [Tableaux](../cpp/arrays-cpp.md)