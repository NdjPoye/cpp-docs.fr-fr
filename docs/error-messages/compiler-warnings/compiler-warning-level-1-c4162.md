---
title: Compilateur avertissement (niveau 1) C4162 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4162
dev_langs: C++
helpviewer_keywords: C4162
ms.assetid: 21ae3c92-501d-4689-ad7d-13753cb65eff
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5e22470de248fdb5371a8d99c5150a1438abab5b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4162"></a>Compilateur avertissement (niveau 1) C4162
'identificateur' : aucune fonction avec liaison C trouvée  
  
 Une fonction avec liaison C est déclarée mais ne peut pas être trouvée.  
  
 Pour résoudre cet avertissement, compilez dans un fichier .c (appelez le compilateur C).  Si vous devez appeler le compilateur C++, placez extern « C » avant la déclaration de fonction.  
  
 L’exemple suivant génère C4162  
  
```  
// C4162.cpp  
// compile with: /c /W1  
unsigned char _bittest(long* a, long b);  
#pragma intrinsic (_bittest)   // C4162  
  
int main() {  
   bool bit;  
   long num = 78002;  
   bit = _bittest(&num, 5);  
}  
```  
  
 Résolution possible :  
  
```  
// C4162b.cpp  
// compile with: /c  
extern "C"  
unsigned char _bittest(long* a, long b);  
#pragma intrinsic (_bittest)  
  
int main() {  
   bool bit;  
   long num = 78002;  
   bit = _bittest(&num, 5);  
}  
```