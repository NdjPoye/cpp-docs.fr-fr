---
title: Erreur du compilateur C2881 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2881
dev_langs: C++
helpviewer_keywords: C2881
ms.assetid: b49c63c2-b064-4d4b-a75e-ddd2af947522
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 96e406dea9a320ec42b0f49a41ef5e531767e82e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2881"></a>Erreur du compilateur C2881
'namespace1' : est déjà utilisé comme alias pour 'EspaceNoms2'  
  
 Vous ne pouvez pas utiliser le même nom en tant qu’alias pour deux espaces de noms.  
  
 L’exemple suivant génère C2881 :  
  
```  
// C2881.cpp  
// compile with: /c  
namespace A {  
   int k;  
}  
  
namespace B {  
   int i;  
}  
  
namespace C = A;  
namespace C = B;   // C2881 C is already an alias for A  
```