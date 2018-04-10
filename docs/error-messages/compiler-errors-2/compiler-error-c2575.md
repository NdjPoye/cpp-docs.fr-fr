---
title: Erreur du compilateur C2575 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C2575
dev_langs:
- C++
helpviewer_keywords:
- C2575
ms.assetid: 9eb45706-37ef-4481-b373-6d193ba13634
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f97fafdfd826318cbb0a914752ec0250562017e9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2575"></a>Erreur du compilateur C2575
'identificateur' : seules les fonctions membres et les bases peuvent être virtuelles  
  
 Une fonction globale ou la classe est déclarée `virtual`. Cette opération n’est pas autorisée.  
  
 L’exemple suivant génère l’erreur C2575 :  
  
```  
// C2575.cpp  
// compile with: /c  
virtual void func() {}   // C2575  
  
void func2() {}  
struct A {  
   virtual void func2(){}  
};  
```