---
title: Erreur du compilateur C2514 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2514
dev_langs: C++
helpviewer_keywords: C2514
ms.assetid: 4b7085e5-6714-4261-80b7-bc72e64ab3e8
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f91dfffe27127cfbff20d7b2e67d097b65cae358
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2514"></a>Erreur du compilateur C2514
'classe' : classe n’a aucun constructeur  
  
 La classe, structure ou union n’a aucun constructeur avec une liste de paramètres qui correspond aux paramètres utilisés pour l’instancier.  
  
 Une classe doit être complètement déclarée avant de pouvoir être instancié.  
  
 L’exemple suivant génère l’erreur C2514 :  
  
```  
// C2514.cpp  
// compile with: /c  
class f;  
  
class g {  
public:  
    g (int x);  
};  
  
class fmaker {  
   f *func1() {  
      return new f(2);   // C2514  
   }  
  
   g *func2() {  
      return new g(2);   // OK  
   }  
};   
```