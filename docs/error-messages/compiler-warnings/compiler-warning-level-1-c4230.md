---
title: Compilateur avertissement (niveau 1) C4230 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4230
dev_langs: C++
helpviewer_keywords: C4230
ms.assetid: a4be8729-74b6-44df-a5ea-e3f45aad0f8f
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c50738e464452599ae8d20eaa3266b75fe301934
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4230"></a>Avertissement du compilateur (niveau 1) C4230
anachronisme utilisé : modificateurs/qualificateurs parsemés ; qualificateur ignoré  
  
 À l’aide d’un qualificateur avant un modificateur Microsoft tel que `__cdecl` est une pratique obsolète.  
  
## <a name="example"></a>Exemple  
  
```  
// C4230.cpp  
// compile with: /W1 /LD  
int __cdecl const function1();   // C4230 const ignored  
```