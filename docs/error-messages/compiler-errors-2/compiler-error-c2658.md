---
title: "L’erreur C2658 erreur de compilateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2658
dev_langs: C++
helpviewer_keywords: C2658
ms.assetid: 638368e8-7893-4a14-abec-13c768a9543a
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 80e7644e949c3d3c605568d820296bbe8310deed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2658"></a>Erreur C2658 erreur de compilateur
'membre' : redéfinition dans un struct/union anonyme  
  
 Deux structures anonymes ou unions contient des déclarations de membre avec le même identificateur, mais avec des types différents. Sous [/Za](../../build/reference/za-ze-disable-language-extensions.md), vous obtiendrez également cette erreur pour les membres avec le même identificateur et le même type.  
  
 L’exemple suivant génère l’erreur C2658 :  
  
```  
// C2658.cpp  
// compile with: /c  
struct X {  
   union { // can be struct too  
      int i;  
   };  
   union {  
      int i;   // Under /Za, C2658  
      // int i not needed here because it is defined in the first union  
   };  
};  
  
struct Z {  
   union {  
      char *i;  
   };  
  
   union {  
      void *i;   // C2658 redefinition of 'i'  
      // try the following line instead  
      // void *ii;  
   };  
};  
```