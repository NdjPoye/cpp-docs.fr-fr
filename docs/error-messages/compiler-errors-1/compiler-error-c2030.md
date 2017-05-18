---
title: Erreur du compilateur C2030 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2030
dev_langs:
- C++
helpviewer_keywords:
- C2030
ms.assetid: 5806cead-64df-4eff-92de-52c9a3f5ee62
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: c76a4fc5de139c2cc9f6802fc66526f291b862a2
ms.contentlocale: fr-fr
ms.lasthandoff: 05/10/2017

---
# <a name="compiler-error-c2030"></a>Erreur du compilateur C2030
un destructeur avec l'accessibilité 'protected private' ne peut pas être membre d'une classe déclarée 'sealed'  
  
 Une classe Windows Runtime déclarée comme `sealed` ne peut pas avoir un destructeur privé protégé. Seuls des destructeurs virtuels publics et non virtuels privés sont autorisés sur les types sealed. Pour plus d’informations, consultez [les classes ou structures](../../cppcx/ref-classes-and-structs-c-cx.md).  
  
 Pour corriger cette erreur, modifiez l'accessibilité du destructeur.
