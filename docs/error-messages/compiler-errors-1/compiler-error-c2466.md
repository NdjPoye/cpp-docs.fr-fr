---
title: Erreur du compilateur C2466 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2466
dev_langs:
- C++
helpviewer_keywords:
- C2466
ms.assetid: 75b251d1-7d0b-4a86-afca-26adedf74486
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 3c3ad19ce37aa51bd6b670da6e857d7eccce04ca
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2466"></a>Erreur du compilateur C2466
Impossible d’allouer un tableau de taille constante 0  
  
 Un tableau est alloué ou déclaré avec une taille égale à zéro. L’expression de constante pour la taille du tableau doit être un entier supérieur à zéro. Une déclaration de tableau avec un indice zéro est autorisée uniquement pour une classe, une structure ou un membre d’union et uniquement avec les extensions Microsoft ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)).  
  
 L’exemple suivant génère l’erreur C2466 :  
  
```  
// C2466.cpp  
// compile with: /c  
int i[0];   // C2466  
int j[1];   // OK  
char *p;  
```
