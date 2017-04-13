---
title: Compilateur avertissement (niveau 1) C4160 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4160
dev_langs:
- C++
helpviewer_keywords:
- C4160
ms.assetid: a9610cb7-cac4-4a74-8b4e-049030ebb92b
caps.latest.revision: 5
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
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: e8662a40b81a18ab4eed2fe50467977879762371
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4160"></a>Avertissement du compilateur (niveau 1) C4160
**#pragma**   
 ***pragma* (pop,...) : n’a pas trouvé l’identificateur '**   
 ***identificateur* '**  
  
 Une instruction pragma dans votre code source tente de dépiler un identificateur qui n’a pas fait l’objet d’un push. Pour éviter cet avertissement, vérifiez que l’identificateur dépilé a bien fait l’objet d’un push.  
  
 L’exemple suivant génère l’erreur C4160 :  
  
```  
// C4160.cpp  
// compile with: /W1  
#pragma pack(push)  
  
#pragma pack(pop, id)   // C4160  
// use identifier when pushing to resolve the warning  
// #pragma pack(push, id)  
  
int main() {  
}  
```
