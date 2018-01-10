---
title: Erreur du compilateur C2589 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2589
dev_langs: C++
helpviewer_keywords: C2589
ms.assetid: 1d7942c7-8a81-4bb4-b272-76a0019e8513
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d0c75c6c42bcaa60f95e6f7e5214bb28ce72f65f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2589"></a>Erreur du compilateur C2589
'identificateur' : jeton non conforme à droite de ' ::'  
  
 Si un nom de classe, structure ou union apparaît à gauche de l’opérateur de résolution de portée (doubles deux-points), le jeton à droite doit être une classe, une structure ou un membre d’union. Sinon, n’importe quel identificateur global peut apparaître à droite.  
  
 L’opérateur de résolution de portée ne peut pas être surchargé.  
  
 L’exemple suivant génère l’erreur C2589 :  
  
```  
// C2589.cpp  
void Test(){}  
class A {};  
void operator :: ();   // C2589  
  
int main() {  
   ::Test();  
}  
```