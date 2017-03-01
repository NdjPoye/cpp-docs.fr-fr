---
title: Erreur du compilateur C3152 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3152
dev_langs:
- C++
helpviewer_keywords:
- C3152
ms.assetid: 4ee6e2cd-5d19-4b73-833d-765c35797e4b
caps.latest.revision: 11
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
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 955f365da967b2fb9499f59fc97489f1302e49a1
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3152"></a>Erreur du compilateur C3152
'construction' : 'mot clé' ne peut s'appliquer qu'à une classe, une structure ou une fonction membre virtuelle  
  
 Certains mots clés ne peuvent être appliqués qu'à une classe C++.  
  
 L'exemple suivant génère l'erreur C3152 et montre comment la corriger :  
  
```  
// C3152.cpp  
// compile with: /clr /c  
ref class C {  
   int (*pfn)() sealed;   // C3152  
   virtual int g() sealed;   // OK  
};  
```  

