---
title: Erreur du compilateur C3136 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3136
dev_langs:
- C++
helpviewer_keywords:
- C3136
ms.assetid: c77103cd-00f7-408e-b74b-4f8562039d31
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 9e6a8e3c958c6c1293b20451f632910001ef24f2
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3136"></a>Erreur du compilateur C3136
'interface' : une interface COM ne peut hériter que d’une autre interface COM, 'interface' n’est pas une interface COM  
  
 Une interface à laquelle vous avez appliqué un [attribut interface](../../windows/interface-attributes.md) hérite d’une interface qui n’est pas une interface COM. Finalement, une interface COM hérite `IUnknown`. N’importe quelle interface précédé d’un attribut d’interface est une interface COM.  
  
 L’exemple suivant génère l’erreur C3136 :  
  
```  
// C3136.cpp  
#include "unknwn.h"  
  
__interface A   // C3136  
// try the following line instead  
// _interface A : IUnknown  
{  
   int a();  
};  
  
[object]  
__interface B : A  
{  
   int aa();  
};  
```
