---
title: "C3084 d’erreur du compilateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3084
dev_langs:
- C++
helpviewer_keywords:
- C3084
ms.assetid: 0362cb70-e24e-476f-a24d-8f5bb97c3afd
caps.latest.revision: 12
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
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 7fb05bf2ebf23446de0552fd06092cb75541d49e
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3084"></a>Erreur du compilateur C3084
'function' : un finaliseur/destructeur ne peut pas avoir la valeur 'keyword'  
  
 Un finaliseur ou un destructeur n’a pas été correctement déclaré.  
  
 Par exemple, un destructeur ne doit pas être marqué comme sealed.  Le destructeur sera inaccessible aux types dérivés.  Pour plus d’informations, consultez [substitutions explicites](../../windows/explicit-overrides-cpp-component-extensions.md) et [destructeurs et finaliseurs dans Comment : définir et consommer des classes et structs (C + c++ / CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3084.  
  
```  
// C3084.cpp  
// compile with: /clr /c  
ref struct R {  
protected:  
   !R() sealed;   // C3084  
   !R() abstract;   // C3084  
   !R();  
};  
```
