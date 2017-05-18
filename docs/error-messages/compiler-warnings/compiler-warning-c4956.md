---
title: Avertissement du compilateur C4956 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4956
dev_langs:
- C++
helpviewer_keywords:
- C4956
ms.assetid: 9154f2d1-d49f-4e07-90d2-0e9bc028011a
caps.latest.revision: 9
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 782735be55c043482679740afa9571ba7b29dfc4
ms.contentlocale: fr-fr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-c4956"></a>Avertissement du compilateur C4956
'type' : ce type n’est pas vérifiable  
  
 Cet avertissement est généré quand [/CLR : safe](../../build/reference/clr-common-language-runtime-compilation.md) est spécifié et que votre code contient un type qui n’est pas vérifiable.  
  
 Pour plus d’informations, consultez [Code pur et vérifiable (C + c++ / CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
 Cet avertissement est émis comme une erreur et peut être désactivé avec le [avertissement](../../preprocessor/warning.md) pragma ou [/wd](../../build/reference/compiler-option-warning-level.md) option du compilateur.  
  
 L’exemple suivant génère l’avertissement C4956.  
  
```  
// C4956.cpp  
// compile with: /clr:safe  
int* p;   // C4956  
```
