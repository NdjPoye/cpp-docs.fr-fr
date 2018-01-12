---
title: Erreur du compilateur C2720 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2720
dev_langs: C++
helpviewer_keywords: C2720
ms.assetid: 9ee3aab7-711b-4f5a-b2f1-cb62b130f1ce
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cfd1e41ea3b9479f07faa9a1cbf0739bc0b7e8b6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2720"></a>Erreur du compilateur C2720  
  
> '*identificateur*' : '*spécificateur*' spécificateur de classe de stockage non conforme sur les membres  
  
La classe de stockage ne peut pas être utilisée sur les membres de classe en dehors de la déclaration. Pour corriger cette erreur, supprimez les éléments inutiles [classe de stockage](../../cpp/storage-classes-cpp.md) spécificateur de la définition de membre en dehors de la déclaration de classe.  
  
## <a name="example"></a>Exemple  
  
L'exemple suivant génère l'erreur C2720 et montre comment la corriger :  
  
```cpp  
// C2720.cpp  
struct S {  
   static int i;  
};  
static S::i;   // C2720 - remove the unneeded 'static' to fix it  
```