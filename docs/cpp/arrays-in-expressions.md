---
title: Tableaux dans les Expressions | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- expressions [C++], arrays in
- arrays [C++], in expressions
ms.assetid: 6e5a795b-d6bd-4e39-b313-6a20d47c4d4b
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 29f6e16e665d8076ed5a1fe593e1bb9437f1406a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="arrays-in-expressions"></a>Tableaux dans les expressions
Lorsqu’un identificateur d’un type tableau s’affiche dans une expression autre que `sizeof`, d’adresse (**&**), ou l’initialisation d’une référence, il est converti en un pointeur vers le premier élément du tableau. Exemple :  
  
```  
char szError1[] = "Error: Disk drive not ready.";  
char *psz = szError1;  
```  
  
 Le pointeur `psz` pointe vers le premier élément du tableau `szError1`. Notez que les tableaux, contrairement aux pointeurs, ne sont pas des valeurs lvalues modifiables. Par conséquent, l'assignation suivante n'est pas conforme :  
  
```  
szError1 = psz;  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Tableaux](../cpp/arrays-cpp.md)