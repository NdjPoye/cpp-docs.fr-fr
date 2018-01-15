---
title: _SCL_SECURE_NO_WARNINGS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
dev_langs: C++
helpviewer_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
ms.assetid: ef0ddea9-7c62-4b53-8b64-5f4fd369776f
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 288af808dfa714c10eeba1f11738cf9db31d70d5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="sclsecurenowarnings"></a>_SCL_SECURE_NO_WARNINGS
Appeler l’une des méthodes potentiellement dangereuses dans la bibliothèque standard C++ provoque un [avertissement du compilateur (niveau 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Pour désactiver cet avertissement, définissez la macro **_SCL_SECURE_NO_WARNINGS** dans votre code :  
  
```  
#define _SCL_SECURE_NO_WARNINGS  
```  
  
## <a name="remarks"></a>Notes  
 Autres façons de désactiver l’avertissement C4996 :  
  
-   Utilisation de l’option de compilateur [/D (définitions de préprocesseur)](../build/reference/d-preprocessor-definitions.md) :  
  
 ```  
    cl /D_SCL_SECURE_NO_WARNINGS [other compiler options] myfile.cpp  
```  
  
-   Utilisation de l’option de compilateur [/w](../build/reference/compiler-option-warning-level.md) :  
  
 ```  
    cl /wd4996 [other compiler options] myfile.cpp  
```  
  
-   Utilisation de la directive [#pragma warning](../preprocessor/warning.md) :  
  
 ```  
 #pragma warning(disable:4996)  
```  
  
 En outre, vous pouvez modifier manuellement le niveau d’avertissement C4996 avec la **Wn\<l >\< n>**  option du compilateur. Par exemple, pour définir l’avertissement C4996 au niveau 4 :  
  
```  
cl /w44996 [other compiler options] myfile.cpp  
```  
  
 Pour plus d’informations, consultez [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, /we, /wo, /Wv, /WX (Niveau d’avertissement)](../build/reference/compiler-option-warning-level.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Bibliothèques sécurisées : bibliothèque standard C++](../standard-library/safe-libraries-cpp-standard-library.md)

