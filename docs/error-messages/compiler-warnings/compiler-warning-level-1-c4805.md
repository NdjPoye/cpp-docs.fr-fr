---
title: Compilateur avertissement (niveau 1) C4805 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4805
dev_langs: C++
helpviewer_keywords: C4805
ms.assetid: 99c7b7e2-272e-4ab5-8580-17c42e62e2ef
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9a466d56a85d3f41696cc1315deab0e49c0eda30
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4805"></a>Avertissement du compilateur (niveau 1) C4805
'operation' : mélange risqué de type 'type' et type 'type' dans l’opération  
  
 Cet avertissement est généré pour les opérations de comparaison entre [bool](../../cpp/bool-cpp.md) et [int](../../c-language/integer-types.md). L’exemple suivant génère l’erreur C4805 :  
  
```  
// C4805.cpp  
// compile with: /W1  
int main() {  
   int i = 1;  
   bool b = true;  
  
   if (i == b) {   // C4805, comparing bool and int variables  
   }  
}  
```