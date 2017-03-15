---
title: Erreur du compilateur C3389 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3389
dev_langs:
- C++
helpviewer_keywords:
- C3389
ms.assetid: eaaffe17-23f2-413c-b1ad-f7220cfa1334
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 6cfe5a03ecbb370eaf290f94ee5e26a5d185a1ae
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3389"></a>Erreur du compilateur C3389
__declspec (Keyword) ne peut pas être utilisé avec/clr : pure ou/CLR : safe  
  
 Le **/CLR : pure** et **/CLR : safe** options du compilateur sont déconseillées dans Visual Studio 2015.  
  
 A [__declspec](../../cpp/declspec.md) modificateur utilisé implique un état par processus.  [/ CLR : pure](../../build/reference/clr-common-language-runtime-compilation.md) implique un par [appdomain](../../cpp/appdomain.md) état.  Ainsi, déclarer une variable avec le `keyword` **__declspec** modificateur et la compilation avec **/CLR : pure** n’est pas autorisée.  
  
 L’exemple suivant génère l’erreur C3389 :  
  
```  
// C3389.cpp  
// compile with: /clr:pure /c  
__declspec(dllexport) int g2 = 0;   // C3389  
```
