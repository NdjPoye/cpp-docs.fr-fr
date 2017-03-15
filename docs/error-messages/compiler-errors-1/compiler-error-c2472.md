---
title: "C2472 d’erreur du compilateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2472
dev_langs:
- C++
helpviewer_keywords:
- C2472
ms.assetid: 3b36bcdc-2ba5-4357-ab88-7545ba0551cd
caps.latest.revision: 7
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
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 058e05e851aed1a31e8f59edcb75c034e186ddaf
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2472"></a>Erreur du compilateur C2472
'function' ne peut pas être généré dans le code managé : 'message' ; compilez avec /clr pour générer une image mixte  
  
 Cette erreur se produit quand des types non pris en charge par le code managé sont utilisés dans un environnement CLR pur. Compilez avec **/clr** pour résoudre l’erreur.  
  
 Le **/CLR : pure** et **/CLR : safe** options du compilateur sont déconseillées dans Visual Studio 2015.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C2472 :  
  
```  
// C2472.cpp  
// compile with: /clr:pure  
// C2472 expected  
  
#include <cstdlib>  
  
int main()  
{  
   int * __ptr32 p32;  
   int * __ptr64 p64;  
  
   p32 = (int * __ptr32)malloc(4);  
   p64 = p32;  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [/CLR (Compilation pour le common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md)
