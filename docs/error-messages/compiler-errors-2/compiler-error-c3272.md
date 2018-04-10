---
title: Erreur du compilateur C3272 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- C3272
dev_langs:
- C++
helpviewer_keywords:
- C3272
ms.assetid: 7cdf254d-f207-4116-a1bf-7386f3b82a6f
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 70c08b38abf3df5820ab2b37064d1f47d358e44e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3272"></a>Erreur du compilateur C3272
'symbole' : le symbole requiert FieldOffset, car il est membre de 'nom_type' défini avec StructLayout(LayoutKind::Explicit)  
  
Quand `StructLayout(LayoutKind::Explicit)` est activé, les champs doivent être marqués avec `FieldOffset`.  
  
L’exemple suivant génère l’erreur C3272 :  
  
```  
// C3272_2.cpp  
// compile with: /clr /c  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[StructLayout(LayoutKind::Explicit)]  
ref struct X  
{  
   int data_;   // C3272  
   // try the following line instead  
   // [FieldOffset(0)] int data_;  
};  
```  
