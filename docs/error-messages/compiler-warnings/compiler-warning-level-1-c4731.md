---
title: Compilateur avertissement (niveau 1) C4731 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4731
dev_langs: C++
helpviewer_keywords: C4731
ms.assetid: 5658c24c-3e6f-4505-835b-1fb92d47cab0
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9d8c59a22166c3f4f44db3bea43e241a2199009d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4731"></a>Avertissement du compilateur (niveau 1) C4731
'pointeur' : Registre de pointeur 'Registre' modifié par le code assembleur inline frame  
  
 Un Registre de pointeur de frame a été modifié. Vous devez enregistrer et restaurer le Registre dans votre assembly bloc ou frame variable intégrée (locale ou un paramètre, selon le Registre modifié), ou votre code peut ne pas fonctionne correctement.  
  
 L’exemple suivant génère l’erreur C4731 :  
  
```  
// C4731.cpp  
// compile with: /W1 /LD  
// processor: x86  
// C4731 expected  
void bad(int p) {  
   __asm  
   {  
      mov ebp, 1  
   }  
  
   if (p == 1)  
   {  
      // ...  
   }  
}  
```  
  
 EBP est le pointeur de frame (FPO n’est pas autorisée) et il est en cours de modification. Lorsque `p` ultérieure référencée, elle est référencée relatif à `EBP`. Mais `EBP` a été remplacé par le code, afin que le programme ne fonctionnera pas correctement et peut même subir une défaillance.