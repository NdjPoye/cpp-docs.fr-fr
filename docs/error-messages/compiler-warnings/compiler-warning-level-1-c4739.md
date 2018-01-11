---
title: Compilateur avertissement (niveau 1) C4739 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4739
dev_langs: C++
helpviewer_keywords: C4739
ms.assetid: 600873b3-7c85-4cd4-944e-cd8e01bfcbb0
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d11002afb2eac0c7f9c6971bca3610463eed0d55
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4739"></a>Avertissement du compilateur (niveau 1) C4739
la référence à la variable ’var’ dépasse la taille de son espace de stockage  
  
 Une valeur a été assignée à une variable, mais la valeur est supérieure à la taille de la variable. La mémoire sera écrite au delà de l’emplacement de mémoire de la variable, et une perte de données est possible.  
  
 Pour résoudre cet avertissement, affectez une valeur uniquement à une variable dont la taille lui permet de contenir la valeur.  
  
 L’exemple suivant génère l’erreur C4739 :  
  
```  
// C4739.cpp  
// compile with: /RTCs /Zi /W1 /c  
char *pc;  
int main() {  
   char c;  
   *(int *)&c = 1;   // C4739  
  
   // OK  
   *(char *)&c = 1;  
}  
```