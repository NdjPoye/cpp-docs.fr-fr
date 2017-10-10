---
title: Erreur du compilateur C2533 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2533
dev_langs:
- C++
helpviewer_keywords:
- C2533
ms.assetid: 5b335652-076c-4824-87c8-a741f64a3ce0
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c21849c7318ac4f169bf7104a478fa57ba7dd040
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2533"></a>Erreur du compilateur C2533
’identificateur’ : type de retour non autorisé pour les constructeurs  
  
 Un constructeur ne peut pas avoir de type de retour (pas même un type de retour `void`).  
  
 Une source courante de cette erreur est un point-virgule manquant entre la fin d'une définition de classe et l'implémentation du premier constructeur. Le compilateur considère la classe comme une définition du type de retour de la fonction constructeur et génère l'erreur C2533.  
  
 L'exemple suivant génère l'erreur C2533 et montre comment la corriger :  
  
```  
// C2533.cpp  
// compile with: /c  
class X {  
public:  
   X();     
};  
  
int X::X() {}   // C2533 - constructor return type not allowed  
X::X() {}   // OK - fix by using no return type  
```
