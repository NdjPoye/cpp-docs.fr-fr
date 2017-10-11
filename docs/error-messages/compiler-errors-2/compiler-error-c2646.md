---
title: Erreur du compilateur C2646 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2646
dev_langs:
- C++
helpviewer_keywords:
- C2646
ms.assetid: 92ff1f02-5eaf-40a5-8b7a-a682f149e967
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 353f65b4d9702ed82ff92eae63fcedaa6adba227
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2646"></a>Erreur du compilateur C2646
une struct ou union anonyme au niveau de la portée globale ou de la portée de l'espace de noms doit être déclarée statique  
  
 Un struct ou une union anonyme possède une portée globale ou une portée d'espace de noms mais n'est pas déclaré(e) `static`.  
  
 L'exemple suivant génère l'erreur C2646 et montre comment la corriger :  
  
```  
// C2646.cpp  
// compile with: /c  
union { int i; };   // C2646 not static  
  
// OK  
static union { int j; };  
union U { int i; };  
```
