---
title: Erreur du compilateur C3286 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3286
dev_langs: C++
helpviewer_keywords: C3286
ms.assetid: 554328c8-cf44-4f7d-a8d2-def74d28ecdd
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ea704fce0aebd3ffa83410104b38ceb5d359a6c6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3286"></a>Erreur du compilateur C3286  
  
> '*spécificateur*' : une variable d’itération ne peut pas avoir de spécificateurs de classe de stockage  
  
Une classe de stockage ne peut pas être spécifiée sur une variable d’itération. Pour plus d’informations, consultez [classes de stockage (C++)](../../cpp/storage-classes-cpp.md) et [pour chacun, dans](../../dotnet/for-each-in.md).  
  
## <a name="example"></a>Exemple  
  
L’exemple suivant génère l’erreur C3286 et montre également l’utilisation correcte.  
  
```cpp  
// C3286.cpp  
// compile with: /clr  
int main() {  
   array<int> ^p = { 1, 2, 3 };  
   for each (static int i in p) {}   // C3286   
   for each (int j in p) {}   // OK  
}  
```