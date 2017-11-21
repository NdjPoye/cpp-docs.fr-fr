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
ms.openlocfilehash: 22643ad7b1e801f2e4b9ee663c73f0d8fb97562d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
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