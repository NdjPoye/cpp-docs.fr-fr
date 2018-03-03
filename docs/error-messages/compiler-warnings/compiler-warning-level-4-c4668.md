---
title: Compilateur avertissement (niveau 4) C4668 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4668
dev_langs:
- C++
helpviewer_keywords:
- C4668
ms.assetid: c6585460-bc4a-4a15-9242-4cbfce53c961
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c8cd54cbc252bf86fdc974fd0e5a87e44d5c853e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4668"></a>Avertissement du compilateur (niveau 4) C4668
'symbole' non défini comme préprocesseur ou macro, remplacement par '0' pour 'directives'  
  
 Un symbole non défini a été utilisé avec une directive de préprocesseur. Le symbole prendra la valeur false. Pour définir un symbole, vous pouvez utiliser la [#define, directive](../../preprocessor/hash-define-directive-c-cpp.md) ou [/D](../../build/reference/d-preprocessor-definitions.md) option du compilateur.  
  
 Cet avertissement est désactivé par défaut. Consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md) pour plus d'informations.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C4668 :  
  
```  
// C4668.cpp  
// compile with: /W4  
#include <stdio.h>  
  
#pragma warning (default : 4668)   // turn warning on  
  
int main()   
{  
    #if q   // C4668, q is not defined  
        printf_s("defined");  
    #else  
        printf_s("undefined");  
    #endif  
}  
```