---
title: Compilateur avertissement (niveau 1) C4325 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4325
dev_langs: C++
helpviewer_keywords: C4325
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ab31150efc02601d7392470198e162e979ac4917
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4325"></a>Avertissement du compilateur (niveau 1) C4325
**attributs pour la section '**   
 ***section* ' ignoré**  
  
 Vous ne pouvez pas modifier les attributs d’une section standard. Exemple :  
  
```  
#pragma section(".sdata", long)  
```  
  
 Ceci remplacerait le `.sdata` section standard qui utilise le **court** type de données avec le **long** type de données.  
  
 Sections standards dont vous ne pouvez pas modifier les attributs incluent,  
  
-   .Data  
  
-   .sdata  
  
-   .BSS  
  
-   .sbss  
  
-   .Text  
  
-   .const  
  
-   .sconst  
  
-   .rdata  
  
-   .srdata  
  
 Des sections supplémentaires peuvent être ajoutées plus tard.  
  
## <a name="see-also"></a>Voir aussi  
 [section](../../preprocessor/section.md)