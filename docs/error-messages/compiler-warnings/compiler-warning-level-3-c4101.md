---
title: Compilateur avertissement (niveau 3) C4101 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4101
dev_langs: C++
helpviewer_keywords: C4101
ms.assetid: d98563cd-9dce-4aae-8f12-bd552a4ea677
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: edd99402978a41a115afa2d96f86abd63d72afa4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4101"></a>Compilateur avertissement (niveau 3) C4101
'identificateur' : variable locale non référencée  
  
 La variable locale n’est jamais utilisée. Cet avertissement se produit dans la situation évidente :  
  
```  
// C4101a.cpp  
// compile with: /W3  
int main() {  
int i;   // C4101  
}  
```  
  
 Toutefois, cet avertissement se produit également lorsque vous appelez un **statique** fonction membre via une instance de la classe :  
  
```  
// C4101b.cpp  
// compile with:  /W3  
struct S {  
   static int func()  
   {  
      return 1;  
   }  
};  
  
int main() {  
   S si;   // C4101, si is never used  
   int y = si.func();  
   return y;  
}  
```  
  
 Dans ce cas, le compilateur utilise les informations sur les `si` pour accéder à la **statique** (fonction), mais l’instance de la classe n’est pas nécessaire d’appeler le **statique** fonction ; par conséquent, l’avertissement. Pour résoudre cet avertissement, vous pouvez :  
  
-   Ajoutez un constructeur, dans lequel le compilateur utilise l’instance de `si` dans l’appel à `func`.  
  
-   Supprimer le **statique** (mot clé) de la définition de `func`.  
  
-   Appelez le **statique** explicitement de fonction : `int y = S::func();`.