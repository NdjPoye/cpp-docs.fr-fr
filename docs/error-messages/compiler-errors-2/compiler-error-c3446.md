---
title: "C3446 d’erreur du compilateur | Documents Microsoft"
ms.custom: 
ms.date: 07/21/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3446
dev_langs:
- C++
helpviewer_keywords:
- C3445
ms.assetid: 33064548-24e4-46f1-beb1-476e3c3b3fbf
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 590f9b4012c7a00cb73a61b0d275ff9c5ee9cf9e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3446"></a>C3446 d’erreur du compilateur  
  
>'*classe*' : un initialiseur de membre par défaut n’est pas autorisé pour un membre d’une classe value  
  
Dans Visual Studio 2015 et antérieur, le compilateur autorisait (mais ignorait) un initialiseur de membre par défaut pour un membre d’une classe value. L’initialisation par défaut d’une classe value initialise systématiquement les membres à zéro ; un constructeur par défaut n’est pas autorisé. Dans Visual Studio 2017, les initialiseurs de membres par défaut déclenchent une erreur de compilateur, comme illustré dans cet exemple :

## <a name="example"></a>Exemple  
 L’exemple suivant génère C3446 dans Visual Studio 2017 et versions ultérieures :  
  
```cpp  
// C3446.cpp  
value struct V
{
       int i = 0; // error C3446: 'V::i': a default member initializer  
                  // is not allowed for a member of a value class
       int j {0}; // C3446           
};
```  
  
Pour corriger l’erreur, supprimez l’initialiseur de :  
  
```cpp  
// C3446b.cpp  
value struct V
{
       int i;  
       int j;
};
```  
  
