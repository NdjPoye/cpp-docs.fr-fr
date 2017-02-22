---
title: "Noms de fichiers longs dans un makefile | Microsoft Docs"
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
  - "noms de fichiers longs"
  - "programme NMAKE, noms de fichiers longs"
ms.assetid: 626d56fc-8879-46ba-9c2d-dd386c78cccc
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Noms de fichiers longs dans un makefile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mettez les noms de fichiers longs entre des guillemets doubles, comme suit :  
  
```  
all : "VeryLongFileName.exe"  
```  
  
## Voir aussi  
 [Contenu d'un makefile](../build/contents-of-a-makefile.md)