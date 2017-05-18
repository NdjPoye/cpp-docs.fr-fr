---
title: Erreur du compilateur C3862 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3862
dev_langs:
- C++
helpviewer_keywords:
- C3862
ms.assetid: ba547366-4189-4077-8c00-ab45e08a9533
caps.latest.revision: 6
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 48dbae62c367616a437db0607d84fa89e8006021
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3862"></a>Erreur du compilateur C3862
'fonction' : Impossible de compiler une fonction non managée avec/clr : pure ou/CLR : safe  
  
 Le **/CLR : pure** et **/CLR : safe** options du compilateur sont déconseillées dans Visual Studio 2015.  
  
 Une compilation avec **/CLR : pure** ou **/CLR : safe** produira une image MSIL uniquement, une image sans code natif (non managé).  Par conséquent, vous ne pouvez pas utiliser le `unmanaged` pragma dans un **/CLR : pure** ou **/CLR : safe** compilation.  
  
 Pour plus d’informations, consultez [/clr (Compilation pour le Common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md) et [managé, non managé](../../preprocessor/managed-unmanaged.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3862 :  
  
```  
// C3862.cpp  
// compile with: /clr:pure /c  
#pragma unmanaged  
void f() {}   // C3862  
```
