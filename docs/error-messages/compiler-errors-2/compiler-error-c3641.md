---
title: Erreur du compilateur C3641 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3641
dev_langs:
- C++
helpviewer_keywords:
- C3641
ms.assetid: e8d3613e-5e8d-46fe-a516-eb7d1de7cd21
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
ms.openlocfilehash: 1f928242a26ed45a48cc9bc19be231e2d0e09a51
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3641"></a>Erreur du compilateur C3641
'fonction' : non valide de convention d’appel 'convention_appel' pour la fonction compilée avec/clr : pure ou/CLR : safe  
  
 Le **/CLR : pure** et **/CLR : safe** options du compilateur sont déconseillées dans Visual Studio 2015.  
  
 Seuls [__clrcall](../../cpp/clrcall.md) convention d’appel est autorisée avec [/CLR : pure](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 L’exemple suivant génère l’erreur C3641 :  
  
```  
// C3641.cpp  
// compile with: /clr:pure /c  
void __cdecl f() {}   // C3641  
```
