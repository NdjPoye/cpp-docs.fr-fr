---
title: Erreur du compilateur C2161 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2161
dev_langs:
- C++
helpviewer_keywords:
- C2161
ms.assetid: d6798821-13bb-4e60-924f-85f7bf955387
caps.latest.revision: 8
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
ms.openlocfilehash: 06b21ad039a8ec8eab076f3bfaaa7aa6ee1df3b7
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2161"></a>Erreur du compilateur C2161
'##' ne peut se trouver à la fin de la définition d’une macro  
  
 La définition d’une macro s’est terminée par un opérateur de collage de jeton (##).  
  
 L’exemple suivant génère l’erreur C2161 :  
  
```  
// C2161.cpp  
// compile with: /c  
#define mac(a,b) a   // OK  
#define mac(a,b) a##   // C2161  
```
