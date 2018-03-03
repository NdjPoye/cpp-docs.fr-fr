---
title: Erreur du compilateur C2110 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2110
dev_langs:
- C++
helpviewer_keywords:
- C2110
ms.assetid: 48fd76ed-90d6-4a60-9c7b-f6ce9355b4ca
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 84f8439a862f049fff902b317c5d185f2898ad54
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2110"></a>Erreur du compilateur C2110
'+' : impossible d’ajouter deux pointeurs  
  
 L’utilisateur a tenté d’ajouter deux valeurs de pointeur avec l’opérateur `+` (signe plus).  
  
 L’exemple suivant génère l’erreur C2110 :  
  
```  
// C2110.cpp  
int main() {  
   int a = 0;  
   int *pa;  
   int *pb;  
   a = pa + pb;   // C2110  
}  
```