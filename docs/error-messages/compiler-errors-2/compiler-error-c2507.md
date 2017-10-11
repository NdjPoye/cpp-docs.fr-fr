---
title: Erreur du compilateur C2507 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2507
dev_langs:
- C++
helpviewer_keywords:
- C2507
ms.assetid: f102aff5-de7d-4c3f-9cac-2ddf9ce02b14
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6320fd9b6642d6be36d59151dd9c3260917d1b61
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2507"></a>Erreur du compilateur C2507
'identificateur' : modificateurs virtuels sur la classe de base trop nombreux  
  
 Une classe ou une structure est déclarée en tant que `virtual` plusieurs fois. Seul `virtual` modificateur peut apparaître pour chaque classe dans une liste de classes de base.  
  
 L’exemple suivant génère l’erreur C2507 :  
  
```  
// C2507.cpp  
// compile with: /c  
class A {};  
class B : virtual virtual public A {};   // C2507  
class C : virtual public A {};   // OK  
```
