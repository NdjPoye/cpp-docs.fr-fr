---
title: Tableaux dans les Expressions | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- expressions [C++], arrays in
- arrays [C++], in expressions
ms.assetid: 6e5a795b-d6bd-4e39-b313-6a20d47c4d4b
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: ec97fba837ffae0a03ff8d4fc3d85c4011aa59c6
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

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
