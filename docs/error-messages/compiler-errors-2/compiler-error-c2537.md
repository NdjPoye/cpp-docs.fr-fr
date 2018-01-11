---
title: Erreur du compilateur C2537 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2537
dev_langs: C++
helpviewer_keywords: C2537
ms.assetid: aee81d8e-300e-4a8b-b6c4-b3828398b34e
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7095511e401dfb1aa703e1d0be4f998e40416c58
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2537"></a>Erreur du compilateur C2537
'spécificateur' : spécification de liaison non conforme  
  
 Causes possibles :  
  
1.  Le spécificateur de liaison n’est pas pris en charge. Seul le spécificateur de liaison « C » est pris en charge.  
  
2.  Une liaison de « C » est spécifiée pour plusieurs fonctions dans un ensemble de fonctions surchargées. Cette opération n’est pas autorisée.  
  
 L’exemple suivant génère l’erreur C2537 :  
  
```  
// C2537.cpp  
// compile with: /c  
extern "c" void func();   // C2537  
extern "C" void func2();   // OK  
```