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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a2efd868160e3ec7e5bf356603cc821a0b07f149
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2030"></a>Erreur du compilateur C2030
un destructeur avec l'accessibilité 'protected private' ne peut pas être membre d'une classe déclarée 'sealed'  
  
 Une classe Windows Runtime déclarée comme `sealed` ne peut pas avoir un destructeur privé protégé. Seuls des destructeurs virtuels publics et non virtuels privés sont autorisés sur les types sealed. Pour plus d’informations, consultez [les classes ou structures](../../cppcx/ref-classes-and-structs-c-cx.md).  
  
 Pour corriger cette erreur, modifiez l'accessibilité du destructeur.
