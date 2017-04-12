---
title: Compilateur avertissement (niveau 2) C4396 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4396
dev_langs:
- C++
helpviewer_keywords:
- C4396
ms.assetid: 7cd6b283-db17-4574-b299-03e0b913ad70
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 84f0628de933344eb23dc6325679abdcd3699c3a
ms.openlocfilehash: 8e0538cc5a1ec9279c4d84cb9e23e0d6fabfd77e
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-2-c4396"></a>Avertissement du compilateur (niveau 2) C4396
'nom' : le spécificateur inline ne peut pas être utilisé lorsqu’une déclaration friend se réfère à une spécialisation d’un modèle de fonction  
  
 Une spécialisation d’un modèle de fonction ne peut pas spécifier un de le [inline](../../cpp/inline-functions-cpp.md) spécificateurs. Le compilateur émet l’avertissement C4396 et ignore le spécificateur inline.  
  
### <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
-   Supprimez le spécificateur `inline`, `__inline`ou `__forceinline` de la déclaration de la fonction friend.  
  
## <a name="example"></a>Exemple  
 L’exemple de code suivant montre une déclaration de fonction friend non valide avec un spécificateur `inline` .  
  
```  
// C4396.cpp  
// compile with: /W2 /c  
  
class X;   
template<class T> void Func(T t, int i);  
  
class X {  
    friend inline void Func<char>(char t, int i);  //C4396  
// try the following line instead  
//    friend void Func<char>(char t, int i);   
    int i;  
};  
```
