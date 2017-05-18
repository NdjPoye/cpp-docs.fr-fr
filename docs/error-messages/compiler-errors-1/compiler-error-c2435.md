---
title: Erreur du compilateur C2435 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2435
dev_langs:
- C++
helpviewer_keywords:
- C2435
ms.assetid: be6aa8f8-579b-42ea-bdd8-2d01393646ad
caps.latest.revision: 12
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 53a3144fe8e87f36a1a5149d292130a9913b646a
ms.contentlocale: fr-fr
ms.lasthandoff: 04/01/2017

---
# <a name="compiler-error-c2435"></a>Erreur du compilateur C2435
'var' : l’initialisation dynamique requiert un CRT managé, Impossible de compiler avec/clr : safe  
  
 Les options de compilateur **/clr:pure** et **/clr:safe** sont dépréciées dans Visual Studio 2015.  
  
 L’initialisation de variable globale de domaine par application exige la compilation du CRT avec `/clr:pure`, qui ne produit pas d’image vérifiable.  
  
 Pour plus d’informations, consultez [appdomain](../../cpp/appdomain.md) et [processus](../../cpp/process.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C2435 :  
  
```  
// C2435.cpp  
// compile with: /clr:safe /c  
int globalvar = 0;   // C2435  
  
__declspec(process)  
int globalvar2 = 0;  
```
