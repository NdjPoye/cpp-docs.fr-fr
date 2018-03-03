---
title: Erreur du compilateur C2084 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2084
dev_langs:
- C++
helpviewer_keywords:
- C2084
ms.assetid: 990b107f-3721-4851-ae8b-4b69a8c149ed
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cf9e0888e0f959d77198efe036c0234c985ea365
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2084"></a>Erreur du compilateur C2084
fonction '*fonction*' a déjà un corps  
  
 La fonction a déjà été définie.  
  
 Dans les versions de Visual C++ antérieures à Visual Studio 2002,  
  
-   Le compilateur accepte plusieurs spécialisations de modèle résolu sur le même type, bien que les définitions supplémentaires ne sont jamais accessibles. Le compilateur détecte maintenant ces définitions multiples.  
  
-   `__int32`et `int` étaient considérées comme des types distincts. Le compilateur traite maintenant `__int32` comme synonyme de `int`. Cela signifie que le compilateur détecte plusieurs définitions si une fonction est surchargée sur les deux `__int32` et `int` et génère une erreur.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C2084 :  
  
```cpp  
// C2084.cpp  
void Func(int);  
void Func(int) {}   // define function  
void Func(int) {}   // C2084 second definition  
```  
  
Pour corriger cette erreur, supprimez la définition en double :  
  
```  
// C2084b.cpp  
// compile with: /c  
void Func(int);  
void Func(int) {}  
```