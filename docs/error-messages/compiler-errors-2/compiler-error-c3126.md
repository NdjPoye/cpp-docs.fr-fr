---
title: Erreur du compilateur C3126 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3126
dev_langs:
- C++
helpviewer_keywords:
- C3126
ms.assetid: e72658a3-5d85-4a31-89a4-dbc3d475973d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 811377ef557cb690dcd8f1cf92b983d9bac60675
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3126"></a>Erreur du compilateur C3126
Impossible de définir une union 'union' à l’intérieur d’un type managé 'type'  
  
 Une union ne peut pas être définie à l’intérieur d’un type managé.  
  
 L’exemple suivant génère l’erreur C3126 :  
  
```  
// C3126_2.cpp  
// compile with: /clr /c  
ref class Test  
{  
   union x  
   {   // C3126  
      int a;  
      int b;  
   };  
};  
```  
