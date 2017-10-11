---
title: Erreur du compilateur C3898 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3898
dev_langs:
- C++
helpviewer_keywords:
- C3898
ms.assetid: d9a90df6-87e4-4fe7-ab01-c226ee86bf10
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c5ff2b3079de90efbf370082be4fee03dbfaab3e
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3898"></a>Erreur du compilateur C3898
'var' : les membres de données de type peuvent uniquement être membres de types managés  
  
 Un [initonly](../../dotnet/initonly-cpp-cli.md) membre de données a été déclaré dans une classe native.  Un `initonly` données membre peut uniquement être déclaré dans une classe CLR.  
  
 L’exemple suivant génère l’erreur C3898 :  
  
```  
// C3898.cpp  
// compile with: /clr  
struct Y1 {  
   initonly  
   static int data_var = 9;   // C3898  
};  
```  
  
 Résolution possible :  
  
```  
// C3898b.cpp  
// compile with: /clr /c  
ref struct Y1 {  
   initonly  
   static int data_var = 9;  
};  
```
