---
title: Erreur du compilateur C2733 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2733
dev_langs: C++
helpviewer_keywords: C2733
ms.assetid: 67f83561-c633-407c-a2ee-f9fd16e165bf
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fb0c21850d93a39047bacfe38592e381e9fb5918
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2733"></a>Erreur du compilateur C2733
seconde liaison C d’une fonction surchargée 'fonction' non autorisée  
  
 Plusieurs fonctions surchargées sont déclarées avec liaison C. Lorsque vous utilisez une liaison C, seule la forme d’une fonction spécifiée peut être externe. Les fonctions surchargées ayant le même nom non décoré, ils ne peuvent pas être utilisés avec les programmes C.  
  
 L’exemple suivant génère l’erreur C2733 :  
  
```  
// C2733.cpp  
extern "C" {  
   void F1(int);  
}  
  
extern "C" {  
   void F1();   // C2733  
   // try the following line instead  
   // void F2();  
}  
```