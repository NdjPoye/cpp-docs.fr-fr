---
title: "L’avertissement C4165 avertissement (niveau 1) du compilateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4165
dev_langs:
- C++
helpviewer_keywords:
- C4165
ms.assetid: f5bed515-2290-4f88-8dab-b45d95fe26ef
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 4ac033535632e94a365aa8dafd849f2ab28a3af7
ms.openlocfilehash: 9f2007a2f43cd7641979b663c58efb3a8e276246
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4165"></a>Avertissement de C4165 du compilateur (niveau 1) d’avertissement.
'HRESULT' est en train d'être converti en 'bool' ; le voulez-vous ?  
  
Lorsque vous utilisez un HRESULT dans un [si](../../cpp/if-else-statement-cpp.md) instruction, le HRESULT sera converti en un [bool](../../cpp/bool-cpp.md) , sauf si vous explicitement un test de la variable comme HRESULT. Cet avertissement est désactivé par défaut.  
  
## <a name="example"></a>Exemple  
L’exemple suivant génère l’avertissement C4165.  
  
```cpp  
// C4165.cpp  
// compile with: /W1  
#include <windows.h>  
#pragma warning(1:4165)  
  
extern HRESULT hr;  
int main() {  
   if (hr) {  
   // try either of the following ...  
   // if (FAILED(hr)) { // C4165 expected  
   // if (hr != S_OK) {  
   }  
}  
```
