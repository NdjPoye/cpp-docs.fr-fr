---
title: Compilateur avertissement (niveau 1) C4530 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4530
dev_langs: C++
helpviewer_keywords: C4530
ms.assetid: a04dcdb2-84db-459d-9e5e-4e743887465f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: adfa006e3b84517601237bbd844ac983115e74ec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4530"></a>Avertissement du compilateur (niveau 1) C4530
Gestionnaire d’exceptions C++ utilisé, mais les sémantiques de déroulement ne sont pas activés. Spécifiez /EHsc  
  
 Gestion des exceptions C++ a été utilisée mais [/EHsc](../../build/reference/eh-exception-handling-model.md) n’a été sélectionné.  
  
 Lorsque l’option /EHsc n’a pas été activée, un objet avec un stockage automatique dans le cadre, entre la fonction de levée de l’exception et la fonction de détection de l’exception ne sera pas détruit. Toutefois, un objet à stockage automatique créé dans un **essayez** ou **catch** bloc sera détruit.  
  
 L’exemple suivant génère l’erreur C4530 :  
  
```  
// C4530.cpp  
// compile with: /W1  
int main() {  
   try{} catch(int*) {}   // C4530  
}  
```  
  
 Compilez l’exemple avec /EHsc pour résoudre l’avertissement.