---
title: "Avertissement du compilateur (niveau 1) C4325 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4325"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4325"
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement du compilateur (niveau 1) C4325
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**attributs pour la section standard '**   
 ***section* ' ignorés**  
  
 Vous ne pouvez pas modifier les attributs d'une section standard.  Par exemple :  
  
```  
#pragma section(".sdata", long)  
```  
  
 Ceci remplacerait la section standard `.sdata` qui utilise le type de données **short** par le type de données **long**.  
  
 Les sections standard dont vous ne pouvez pas modifier les attributs sont notamment,  
  
-   .data  
  
-   .sdata  
  
-   .bss  
  
-   .sbss  
  
-   .text  
  
-   .const  
  
-   .sconst  
  
-   .rdata  
  
-   .srdata  
  
 Des sections supplémentaires peuvent éventuellement être ajoutées plus tard.  
  
## Voir aussi  
 [section](../../preprocessor/section.md)