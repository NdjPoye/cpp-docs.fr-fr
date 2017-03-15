---
title: Erreur du compilateur C3808 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3808
dev_langs:
- C++
helpviewer_keywords:
- C3808
ms.assetid: 2ee8ac97-3ea4-417a-8710-be73a7f98cf4
caps.latest.revision: 5
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
ms.openlocfilehash: 989f17e8f59afc6a04ed4101204053fc971c6a62
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3808"></a>Erreur du compilateur C3808
'type' : une classe avec l’attribut ComImport ne peut pas définir le membre 'member', abstrait uniquement ou les fonctions dllimport sont autorisées  
  
 Un type dérivé de <xref:System.Runtime.InteropServices.ComImportAttribute>ne peut pas définir `member`.</xref:System.Runtime.InteropServices.ComImportAttribute>  
  
 Le **/CLR : pure** et **/CLR : safe** options du compilateur sont déconseillées dans Visual Studio 2015.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3808 :.  
  
```  
// C3808.cpp  
// compile with: /c /clr:pure user32.lib  
using namespace System::Runtime::InteropServices;  
  
[System::Runtime::InteropServices::ComImportAttribute()]  
ref struct S1 {  
   int f() {}   // C3808  
   virtual int g() abstract;   // OK  
  
   [DllImport("msvcrt.dll")]  
   int printf(System::String ^, int i);   // OK  
};  
```
