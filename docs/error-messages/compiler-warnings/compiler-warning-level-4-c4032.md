---
title: "Du compilateur (niveau 4) d’avertissement C4032 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4032
dev_langs: C++
helpviewer_keywords: C4032
ms.assetid: 70dd0c85-0239-43f9-bb06-507f6a57d206
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9da389e4bc52cb84d331b9005b4b62d2c24ef868
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4032"></a>Du compilateur (niveau 4) d’avertissement C4032
le paramètre formel 'nombre' a un type différent lors de sa promotion  
  
 Le type de paramètre n’est pas compatible, via les promotions par défaut, avec le type d’une déclaration précédente.  
  
 Il s’agit d’une erreur en C ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) et un avertissement avec les extensions Microsoft (/Ze).  
  
## <a name="example"></a>Exemple  
  
```  
// C4032.c  
// compile with: /W4  
void func();  
void func(char);   // C4032, char promotes to int  
  
int main()  
{  
}  
```