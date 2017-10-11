---
title: Erreur du compilateur C2447 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2447
dev_langs:
- C++
helpviewer_keywords:
- C2447
ms.assetid: d1bd6e9a-ee42-4510-ae5e-6b0378f7b931
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 20f9e3259b355a40875bd9fc06f04fe2bb3147d0
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2447"></a>Erreur du compilateur C2447
'{' : en-tête de fonction manquant (liste formelle à l'ancien format ?)  
  
 Le compilateur a rencontré une accolade ouvrante inattendue au niveau de l'étendue globale. Dans la plupart des cas, cela est dû à un en-tête de fonction incorrect, une déclaration mal placée ou un point-virgule égaré. Pour résoudre ce problème, vérifiez que l'accolade ouvrante suit un en-tête de fonction correct, et qu'elle n'est pas précédée d'une déclaration ou d'un point-virgule égaré.  
  
 Cette erreur peut également être provoquée par une liste d'arguments formels en langage C à l'ancien format. Pour résoudre ce problème, refactorisez la liste d'arguments afin d'utiliser le style moderne, c'est-à-dire entre parenthèses.  
  
 L’exemple suivant génère C2447 :  
  
```  
// C2447.cpp  
int c;  
{}       // C2447  
```
