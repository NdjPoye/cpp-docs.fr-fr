---
title: Avertissement du compilateur C4958 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4958
dev_langs:
- C++
helpviewer_keywords:
- C4958
ms.assetid: e79b9e9c-d572-4a3a-a3b6-60962b70864a
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 7deb92709adbb5a10148c092985e9a7c9f463c0c
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-c4958"></a>Avertissement du compilateur C4958
'opération' : l’opération arithmétique de pointeur n’est pas vérifiable  
  
 L’utilisation d’une opération arithmétique de pointeur produira une image non vérifiable.  
  
 Pour plus d’informations, consultez [Code pur et vérifiable (C + c++ / CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
 Cet avertissement est émis comme une erreur et peut être désactivé avec le [avertissement](../../preprocessor/warning.md) pragma ou [/wd](../../build/reference/compiler-option-warning-level.md) option du compilateur.  
  
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
  
 Le compilateur implémente des opérations de tableau avec l’opération arithmétique de pointeur. Par conséquent, les tableaux natifs ne sont pas vérifiables ; utilisez plutôt un tableau CLR. Pour plus d’informations, consultez [tableau](../../windows/arrays-cpp-component-extensions.md).  
  
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
