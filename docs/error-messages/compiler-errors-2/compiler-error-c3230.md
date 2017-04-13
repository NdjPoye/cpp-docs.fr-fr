---
title: Erreur du compilateur C3230 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3230
dev_langs:
- C++
helpviewer_keywords:
- C3230
ms.assetid: 5ec53f25-59f6-4801-81e7-7b68bf04994d
caps.latest.revision: 7
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
ms.openlocfilehash: f822a45d4b0036d4f603422d7ba7adca2f570407
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3230"></a>Erreur du compilateur C3230
'fonction' : l’argument de type de modèle de 'modèle' ne peut pas contenir de paramètre de type générique : 'paramètre'  
  
 Les modèles sont instanciés au moment de la compilation, mais les génériques sont instanciés au moment de l’exécution. Ainsi, il n’est pas possible de générer du code générique pouvant appeler le modèle, car celui-ci ne peut pas être instancié au moment de l’exécution quand le type générique est enfin connu.  
  
 L’exemple suivant génère l’erreur C3230 :  
  
```  
// C3230.cpp  
// compile with: /clr /LD  
template <class S>   
void f(S t);  
  
generic <class U>  
ref class C {  
   void f1(U x) {  
      f(x);   // C3230  
   }  
};  
```
