---
title: Compilateur avertissement (niveau 1) C4810 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4810
dev_langs:
- C++
helpviewer_keywords:
- C4810
ms.assetid: 39e2cae0-9c1c-4ac1-aaa0-5f661d06085b
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
ms.openlocfilehash: af66e9908d27b1f49680c72a14ad1c1b5ddf948e
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4810"></a>Avertissement du compilateur (niveau 1) C4810
valeur de pragma pack(show) == n  
  
 Cet avertissement est émis lorsque vous utilisez la **afficher** possibilité du [pack](../../preprocessor/pack.md) pragma. *n* est la valeur actuelle du pragma pack.  
  
 Par exemple, le code suivant montre comment l’avertissement C4810 fonctionne avec le pragma pack :  
  
```  
// C4810.cpp  
// compile with: /W1 /LD  
// C4810 expected  
#pragma pack(show)  
#pragma pack(4)  
#pragma pack(show)  
```
