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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: af959252ce5b404d8646ad61e02c5e480b41ed83
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3862"></a>Erreur du compilateur C3862
'fonction' : Impossible de compiler une fonction non managée avec/clr : pure ou/CLR : safe  
  
 Les options de compilateur **/clr:pure** et **/clr:safe** sont dépréciées dans Visual Studio 2015.  
  
 Une compilation avec **/CLR : pure** ou **/CLR : safe** produira une image MSIL uniquement, une image avec aucune du code natif (non managé).  Par conséquent, vous ne pouvez pas utiliser le `unmanaged` pragma dans un **/CLR : pure** ou **/CLR : safe** compilation.  
  
 Pour plus d’informations, consultez [/clr (Compilation pour le Common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md) et [managé, non managé](../../preprocessor/managed-unmanaged.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3862 :  
  
```  
// C3862.cpp  
// compile with: /clr:pure /c  
#pragma unmanaged  
void f() {}   // C3862  
```
