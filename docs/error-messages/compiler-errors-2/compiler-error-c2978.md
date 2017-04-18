---
title: Erreur du compilateur C2978 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2978
dev_langs:
- C++
helpviewer_keywords:
- C2978
ms.assetid: 5e7bee82-e266-4ccd-ad2e-ee89606ec5bf
caps.latest.revision: 6
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
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: e34fc28dd4b4bae71f2244e8539d69f1b775303c
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2978"></a>Erreur du compilateur C2978
erreur de syntaxe : 'mot_clé1' ou 'mot_clé2' attendu ; type 'mot_clé3' trouvé ; les paramètres sans type ne sont pas pris en charge dans les génériques  
  
 Une classe générique a été déclarée incorrectement. Consultez [génériques](../../windows/generics-cpp-component-extensions.md)pour plus d’informations.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C2978.  
  
```  
// C2978.cpp  
// compile with: /clr /c  
generic <ref class T>   // C2978  
// try the following line instead  
// generic <typename T>   // OK  
ref class Utils {  
   static void sort(T elems, size_t size);  
};  
  
generic <int>  
// try the following line instead  
// generic <class T>  
ref class Utils2 {  
   static void sort(T elems, size_t size);  
};  
```
