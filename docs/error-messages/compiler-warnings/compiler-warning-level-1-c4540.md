---
title: Compilateur avertissement (niveau 1) C4540 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4540
dev_langs:
- C++
helpviewer_keywords:
- C4540
ms.assetid: 8085e748-5f4d-43c2-b06d-eaf794edbf72
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: aaaef1edaa6af093ae03fe69231a9686e3d087a7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4540"></a>Avertissement du compilateur (niveau 1) C4540
utilisé de dynamic_cast pour convertir une base ambiguë ou inaccessible ; test d’exécution échouera ('type1' en 'type2')  
  
 Vous avez utilisé `dynamic_cast` convertir d’un type à un autre. Le compilateur a déterminé que le cast échouerait toujours (retourner **NULL**) parce qu’une classe de base est inaccessible (`private`, par exemple) ou ambiguë (apparaît plusieurs fois dans la hiérarchie de classes, par exemple).  
  
 Voici un exemple de cet avertissement. Classe **B** est dérivé de la classe **A**. Le programme utilise `dynamic_cast` pour effectuer un cast à partir de la classe **B** (la classe dérivée) pour la classe **A**, qui continue d’échouer, car classe **B** est `private` et par conséquent inaccessible. Modification d’accès de **A** à **public** résout l’avertissement.  
  
```  
// C4540.cpp  
// compile with: /W1  
  
struct A {   
   virtual void g() {}  
};  
  
struct B : private A {  
   virtual void g() {}  
};  
  
int main() {  
   B b;  
   A * ap = dynamic_cast<A*>(&b);   // C4540  
}  
```