---
title: Erreur du compilateur C2191 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2191
dev_langs:
- C++
helpviewer_keywords:
- C2191
ms.assetid: 051b8350-e5de-4f51-ab6e-96d32366bcef
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 8c8f1848fedf7bf811a335043693980855293694
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2191"></a>Erreur du compilateur C2191
seconde liste de paramètres plus longue que la première  
  
 Une fonction C a été déclarée une seconde fois avec une liste de paramètres plus longue. C ne prend pas en charge les fonctions surchargées.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C2191 :  
  
```  
// C2191.c  
// compile with: /Za /c  
void func( int );  
void func( int, float );   // C2191 different parameter list  
void func2( int, float );   // OK  
```
