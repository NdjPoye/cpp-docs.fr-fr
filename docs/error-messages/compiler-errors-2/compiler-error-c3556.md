---
title: Erreur du compilateur C3556 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3556
dev_langs:
- C++
helpviewer_keywords:
- C3556
ms.assetid: 9b002dcc-494e-414f-9587-20c2a0a39333
caps.latest.revision: 6
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
ms.openlocfilehash: d4612c76c662cb1f271e2c85c9403bf957e72dbc
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3556"></a>Erreur du compilateur C3556
'expression' : argument incorrect pour 'decltype'  
  
 Le compilateur ne peut pas déduire le type de l’expression qui représente l’argument du spécificateur de type `decltype(``expression``)` . Dans l’exemple de code suivant, le compilateur ne peut pas déduire le type de l’argument `myFunction` car `myFunction` est surchargé.  
  
```  
void myFunction();  
void myFunction(int);  
decltype(myFunction); // C3556  
```
