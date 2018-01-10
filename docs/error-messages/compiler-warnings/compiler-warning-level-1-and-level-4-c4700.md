---
title: Compilateur avertissement (niveaux 1 et 4) C4700 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4700
dev_langs: C++
helpviewer_keywords: C4700
ms.assetid: 2da0deb4-77dd-4b05-98d3-b78d74ac4ca7
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 14882157fd745c05f38943fae589636a486fd94d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-and-level-4-c4700"></a>Avertissement du compilateur (niveaux 1 et 4) C4700
variable locale non initialisée 'name' utilisé  
  
 Vous avez utilisé la variable locale *nom* sans première lui assigner une valeur, ce qui peut entraîner des résultats imprévisibles.  
  
 L’exemple suivant génère l’erreur C4700 :  
  
```  
// C4700.cpp  
// compile with: /W1  
int main() {  
   int i;  
   return i;   // C4700  
}  
```  
  
 Sous [/CLR : safe](../../build/reference/clr-common-language-runtime-compilation.md) il s’agit d’un avertissement de niveau 4.  L’exemple suivant génère l’erreur C4700 :  
  
```  
// C4700b.cpp  
// compile with: /W4 /clr:safe /c  
using namespace System;  
int main() {  
   Int32^ bi;  
   return *bi;   // C4700  
}  
```