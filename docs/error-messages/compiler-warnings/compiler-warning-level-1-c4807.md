---
title: Compilateur avertissement (niveau 1) C4807 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4807
dev_langs:
- C++
helpviewer_keywords:
- C4807
ms.assetid: 089c9f87-fd81-402e-9826-66a8ef1ef1fe
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: af604a1a045b9dbef7b3c27f9c7aabd0040aa318
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4807"></a>Avertissement du compilateur (niveau 1) C4807
'operation' : mélange risqué de type 'type' et champ de bits signé de type 'type'  
  
 Cet avertissement est généré lors de la comparaison d’un champ de bits signé à un bit avec une variable `bool` . Un champ de bits signé à un bit peut seulement contenir les valeurs -1 ou 0. Il est risqué de le comparer à `bool`. Aucun avertissement n’est généré sur la combinaison de `bool` et de champs de bits non signés à un bit, car ils sont identiques à `bool` et ne peuvent contenir que 0 ou 1.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C4807 :  
  
```  
// C4807.cpp  
// compile with: /W1  
typedef struct bitfield {  
   signed mybit : 1;  
} mybitfield;  
  
int main() {  
   mybitfield bf;  
   bool b = true;  
  
   // try..  
   // int b = true;  
  
   bf.mybit = -1;  
   if (b == bf.mybit) {   // C4807  
      b = false;  
   }  
}  
```