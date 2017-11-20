---
title: Erreur du compilateur C3041 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3041
dev_langs: C++
helpviewer_keywords: C3041
ms.assetid: 9df1ae44-3ac7-4c6c-899f-f35ffe7ccf0d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: be6182f557b2a9ca0985216935fcea654a3ea36a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3041"></a>Erreur du compilateur C3041
'variable' : la variable de la clause 'copyprivate' doit être privée dans un contexte englobant  
  
 Une variable passée à [copyprivate](../../parallel/openmp/reference/copyprivate.md) ne peut pas être partagée dans le contexte englobant.  
  
 L’exemple suivant génère l’erreur C3041 :  
  
```  
// C3041.cpp  
// compile with: /openmp /c  
#include "omp.h"  
double d;  
int main() {  
   #pragma omp parallel shared(d)  
   // try the following line instead  
   // #pragma omp parallel private(d)  
   {  
      // or don't make d copyprivate  
      #pragma omp single copyprivate(d)   // C3041  
      {  
      }  
   }  
}  
```