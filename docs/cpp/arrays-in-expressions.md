---
title: Tableaux dans les Expressions | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- expressions [C++], arrays in
- arrays [C++], in expressions
ms.assetid: 6e5a795b-d6bd-4e39-b313-6a20d47c4d4b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e3e57a97d9be3ef6245c09c6112caf72318fe784
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="arrays-in-expressions"></a>Tableaux dans les expressions
Lorsqu’un identificateur d’un type tableau s’affiche dans une expression autre que `sizeof`, d’adresse (**&**), ou l’initialisation d’une référence, il est converti en un pointeur vers le premier élément du tableau. Par exemple :  
  
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