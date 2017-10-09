---
title: Erreur du compilateur C2010 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2010
dev_langs:
- C++
helpviewer_keywords:
- C2010
ms.assetid: 5795ed1d-e206-410b-b7b4-528d125c67b4
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0863e96dfc137cf262fe1aef977c83dc592b798c
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2010"></a>Erreur du compilateur C2010
'caractère' : inattendu dans la liste de paramètres formels de macro  
  
 Le caractère est utilisé de manière incorrecte dans la liste de paramètres formels d’une définition de macro. Supprimez le caractère pour résoudre l’erreur.  
  
 L’exemple suivant génère l’erreur C2010 :  
  
```  
// C2010.cpp  
// compile with: /c  
#define mymacro(a|) (2*a)   // C2010  
#define mymacro(a) (2*a)   // OK  
```
