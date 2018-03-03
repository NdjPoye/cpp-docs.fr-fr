---
title: Compilateur avertissement (niveau 4) C4434 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4434
dev_langs:
- C++
helpviewer_keywords:
- C4434
ms.assetid: 24b8785e-353a-4c37-8bed-ed61001a871d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a9499d145263c3bbb1bd5aac948c6be9e4db48d2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4434"></a>Avertissement du compilateur (niveau 4) C4434
un constructeur de classe doit avoir un accès privé ; la modification d’un accès privé  
  
 L’erreur C4434 indique que le compilateur a modifié l’accessibilité d’un constructeur statique. Les constructeurs statiques doivent avoir un accès privé, car ils sont uniquement destinés à être appelé par le common language runtime. Pour plus d’informations, consultez [constructeurs statiques](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Static_constructors).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C4434.  
  
```  
// C4434.cpp  
// compile with: /W4 /c /clr  
public ref struct R {  
   static R(){}   // C4434  
};  
```