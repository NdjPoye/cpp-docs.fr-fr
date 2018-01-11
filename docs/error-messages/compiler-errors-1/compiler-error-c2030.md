---
title: Erreur du compilateur C2030 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2030
dev_langs: C++
helpviewer_keywords: C2030
ms.assetid: 5806cead-64df-4eff-92de-52c9a3f5ee62
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c025fe57d411ae4744a10fe9bc062b336e189e83
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2030"></a>Erreur du compilateur C2030
un destructeur avec l'accessibilité 'protected private' ne peut pas être membre d'une classe déclarée 'sealed'  
  
 Une classe Windows Runtime déclarée comme `sealed` ne peut pas avoir un destructeur privé protégé. Seuls des destructeurs virtuels publics et non virtuels privés sont autorisés sur les types sealed. Pour plus d’informations, consultez [les classes ou structures](../../cppcx/ref-classes-and-structs-c-cx.md).  
  
 Pour corriger cette erreur, modifiez l'accessibilité du destructeur.