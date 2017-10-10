---
title: Erreur du compilateur C2803 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2803
dev_langs:
- C++
helpviewer_keywords:
- C2803
ms.assetid: 2cdbe374-8cc4-4c4e-ba15-062a7479e937
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: efa9efa2dc204d302f69d873c0199d4431efccb1
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2803"></a>Erreur du compilateur C2803
'operator opérateur' doit avoir au moins un paramètre de type classe  
  
 L’opérateur surchargé ne dispose pas d’un paramètre de type de classe.  
  
 Vous devez passer au moins un paramètre par référence (ne pas à l’aide de pointeurs, mais des références) ou par valeur pour pouvoir écrire » une < b » (un de la classe de type A et b).  
  
 Si les deux paramètres sont des pointeurs sera une pure comparaison d’adresses de pointeur et n’utilise pas la conversion définie par l’utilisateur.  
  
 L’exemple suivant génère l’erreur C2803 :  
  
```  
// C2803.cpp  
// compile with: /c  
class A{};  
bool operator< (const A *left, const A *right);   // C2803  
// try the following line instead  
// bool operator< (const A& left, const A& right);  
```
