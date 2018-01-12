---
title: Erreur du compilateur C2603 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2603
dev_langs: C++
helpviewer_keywords: C2603
ms.assetid: 9ca520d0-f082-4b65-933d-17c3bcf8b02c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c06c5747a3d785242e8b926fe6e1eaa251a2d8b4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2603"></a>Erreur du compilateur C2603  
  
> '*fonction*' : trop d’objets static de portée de bloc avec constructeur/destructeurs dans la fonction  
  
Dans les versions du compilateur Visual C++ avant Visual Studio 2015, ou lorsque le [/Zc : threadsafeinit](../../build/reference/zc-threadsafeinit-thread-safe-local-static-initialization.md) option du compilateur est spécifiée, il existe une limite de 31 sur le nombre d’objets statiques, vous pouvez avoir dans une fonction inline visible de l’extérieur .  
  
Pour résoudre ce problème, nous vous recommandons de vous adoptez une version plus récente de l’ensemble d’outils du compilateur Visual C++, ou, si possible, supprimez l’option de compilateur/Zc : threadsafeinit. Si ce n’est pas possible, envisagez de combiner vos objets statiques. Si les objets sont du même type, envisagez d’utiliser un seul tableau statique de ce type et faire référence à des membres individuels en fonction des besoins.
  
## <a name="example"></a>Exemple  
  
Le code suivant génère C2603 et illustre une façon de pour résoudre ce problème :  
  
```cpp  
// C2603.cpp  
// Compile by using: cl /W4 /c /Zc:threadSafeInit- C2603.cpp
struct C { C() {} };  
extern inline void f1() {  
    static C C01, C02, C03, C04, C05, C06, C07, C08, C09, C10;
    static C C11, C12, C13, C14, C15, C16, C17, C18, C19, C20;
    static C C21, C22, C23, C24, C25, C26, C27, C28, C29, C30, C31;  
    static C C32;   // C2603 Comment this line out to avoid error  
}  
```
