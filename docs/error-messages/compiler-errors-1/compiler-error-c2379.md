---
title: Erreur du compilateur C2379 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2379
dev_langs:
- C++
helpviewer_keywords:
- C2379
ms.assetid: 37dc3015-a4af-4341-bbf3-da6150df7e51
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 69be5132451269f7eba9c2e9186a9c25d4629ae7
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2379"></a>Erreur du compilateur C2379
nombre de paramètres formels a un type différent lors de sa promotion  
  
 Le type du paramètre spécifié n’est pas compatible, via les promotions par défaut, avec le type d’une déclaration précédente. Il s’agit d’une erreur en C ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) et un avertissement avec les extensions Microsoft (**/Ze**).  
  
 L’exemple suivant génère C2379 :  
  
```  
// C2379.c  
// compile with: /Za  
void func();  
void func(char);   // C2379, char promotes to int  
```
