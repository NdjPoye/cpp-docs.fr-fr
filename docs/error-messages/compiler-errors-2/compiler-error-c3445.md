---
title: "C3445 d’erreur du compilateur | Documents Microsoft"
ms.custom: 
ms.date: 04/10/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3445
dev_langs:
- C++
helpviewer_keywords:
- C3445
ms.assetid: 0d272bfc-136b-4025-a9ba-5e4eea5f8215
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: e880eca87816973d531a2662486dde0ae7c77987
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3445"></a>C3445 d’erreur du compilateur
initialisation de liste copie de '*type*' ne peut pas utiliser un constructeur explicite  
  
Selon la norme ISO C ++ 17 standard, le compilateur est requis pour prendre en compte un constructeur explicite pour la résolution de surcharge dans l’initialisation de liste de copie, mais il doit déclencher une erreur si cette surcharge est choisie.  
  
À partir de Visual Studio 2017, le compilateur recherche des erreurs liées à la création d’objets à l’aide d’une liste d’initialiseurs non trouvées par Visual Studio 2015. Ces erreurs peuvent entraîner se bloque ou un comportement indéfini lors de l’exécution.

## <a name="example"></a>Exemple  
 L’exemple suivant génère C3445.  
  
```cpp  
// C3445.cpp  
struct A
{
    explicit A(int) {} 
    A(double) {}
};

int main()
{
    A a1 = { 1 };     // error C3445: copy-list-initialization of 
                      //     'A' cannot use an explicit constructor
}
```  
  
Pour corriger l’erreur, utilisez à la place une initialisation directe :  
  
```cpp  
// C3445b.cpp  
struct A
{
    explicit A(int) {} 
    A(double) {}
};

int main()
{
    A a1{ 1 };
}  
```  
  
