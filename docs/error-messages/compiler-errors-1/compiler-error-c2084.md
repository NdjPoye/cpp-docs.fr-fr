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
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 653dc7a4a5d330efc89942fbe4ddd07bff81f770
ms.contentlocale: fr-fr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2084"></a>Erreur du compilateur C2084
fonction '*fonction*' a déjà un corps  
  
 La fonction a déjà été définie.  
  
 Dans les versions de Visual C++ antérieures à Visual Studio 2002,  
  
-   Le compilateur accepte plusieurs spécialisations de modèle résolu sur le même type, bien que les définitions supplémentaires ne sont jamais accessibles. Le compilateur détecte maintenant ces définitions multiples.  
  
-   `__int32`et `int` étaient considérées comme des types distincts. Le compilateur traite maintenant `__int32` comme synonyme de `int`. Cela signifie que le compilateur détecte plusieurs définitions si une fonction est surchargée sur les deux `__int32` et `int` et génère une erreur.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère le C2084 :  
  
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
