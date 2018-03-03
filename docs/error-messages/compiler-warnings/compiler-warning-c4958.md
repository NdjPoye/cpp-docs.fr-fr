---
title: Avertissement du compilateur C4958 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4958
dev_langs:
- C++
helpviewer_keywords:
- C4958
ms.assetid: e79b9e9c-d572-4a3a-a3b6-60962b70864a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4de819b0c18e141061f5d180f24558946bbf156b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-c4958"></a>Avertissement du compilateur C4958
'opération' : l’opération arithmétique de pointeur n’est pas vérifiable  
  
 L’utilisation d’une opération arithmétique de pointeur produira une image non vérifiable.  
  
 Pour plus d’informations, consultez [Code pur et vérifiable (C + c++ / CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
 Cet avertissement, qui s’affiche comme une erreur, peut être désactivé avec le pragma [warning](../../preprocessor/warning.md) ou l’option du compilateur [/wd](../../build/reference/compiler-option-warning-level.md) .  
  
 L’exemple suivant génère l’avertissement C4958 :  
  
```  
// C4958.cpp  
// compile with: /clr:safe  
// #pragma warning( disable : 4958 )  
using namespace System;  
  
int main( ) {  
   Int32 arr[] = new Int32[10];  
   Int32* p = &arr[0];  
   p++;   // C4958  
}  
```  
  
 Le compilateur implémente des opérations de tableau avec l’opération arithmétique de pointeur. Par conséquent, les tableaux natifs ne sont pas vérifiables ; utilisez plutôt un tableau CLR. Pour plus d'informations, consultez [tableau](../../windows/arrays-cpp-component-extensions.md).  
  
 L’exemple suivant génère l’avertissement C4958 :  
  
```  
// C4958b.cpp  
// compile with: /clr:safe  
// #pragma warning( disable : 4958 )  
  
int main() {  
   int array[5];  
   array[4] = 0;   // C4958  
}  
```