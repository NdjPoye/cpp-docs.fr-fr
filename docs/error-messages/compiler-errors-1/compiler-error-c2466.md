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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3a41ea550abff9e48973452996cf5621e6bc4c42
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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