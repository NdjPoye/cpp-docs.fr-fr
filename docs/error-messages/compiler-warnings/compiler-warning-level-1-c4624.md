---
title: Compilateur avertissement (niveau 1) C4624 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4624
dev_langs:
- C++
helpviewer_keywords:
- C4624
ms.assetid: 14f61769-d92e-482b-9515-debd87b30a66
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2a3acf93e1609b6a53f6654afb83a51bad49da84
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4624"></a>Avertissement du compilateur (niveau 1) C4624
'classe dérivée' : le destructeur a été défini de manière implicite comme supprimé car un destructeur de la classe de base est inaccessible ou supprimé  
  
 Un destructeur n'était pas accessible ou était supprimé dans une classe de base et n'a donc pas été généré pour une classe dérivée. Toute tentative pour créer un objet de ce type dans la pile provoquera une erreur du compilateur.  
  
 L'exemple suivant génère l'erreur C4624 et montre comment la corriger :  
  
```  
// C4624.cpp  
// compile with: /W1 /c  
class B {  
// Uncomment the following line to fix.  
// public:  
   ~B();  
};  
  
class D : public B {};   // C4624 B's destructor not public  
```