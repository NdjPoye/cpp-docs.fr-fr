---
title: Compilateur avertissement (niveau 1) C4461 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4461
dev_langs:
- C++
helpviewer_keywords:
- C4461
ms.assetid: 104ffecc-3dd4-4cb1-89a8-81154fbe46d9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b3b3a64ac5d7bcfbc912c63abf57769fe6da2d40
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4461"></a>Avertissement du compilateur (niveau 1) C4461
'type' : cette classe a un finaliseur 'finaliseur' mais aucun destructeur 'dtor'  
  
 La présence d’un finaliseur dans un type implique des ressources à supprimer. Sauf si un finaliseur est explicitement appelé à partir destructeur du type, le common language runtime détermine à quel moment exécuter le finaliseur, une fois votre objet est hors de portée.  
  
 Si vous définissez un destructeur dans le type et appelez explicitement le finaliseur à partir du destructeur, vous pouvez exécuter de façon déterministe votre finaliseur.  
  
 Pour plus d’informations, consultez [destructeurs et finaliseurs](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C4461.  
  
```  
// C4461.cpp  
// compile with: /W1 /clr /c  
ref class A {  
protected:  
   !A() {}   // C4461  
};  
  
// OK  
ref struct B {  
   ~B() {  
      B::!B();  
   }  
  
   !B() {}  
};  
```