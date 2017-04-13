---
title: Erreur du compilateur C2998 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2998
dev_langs:
- C++
helpviewer_keywords:
- C2998
ms.assetid: 8193d491-b5d9-4477-acb1-cf166889c070
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
ms.openlocfilehash: 03deb6d3624883cbe3fded5366d1ae3487bf12e5
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2998"></a>Erreur du compilateur C2998
'identifier' : ne peut pas être une définition de modèle  
  
 Le compilateur n’a pas pu traiter la syntaxe utilisée dans la définition de modèle.  
  
 L’exemple suivant génère l’erreur C2998 :  
  
```  
// C2998.cpp  
// compile with: /c  
template <class T> int x = 1018; // C2998  
```
