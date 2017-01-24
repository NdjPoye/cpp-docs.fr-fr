---
title: "_SCL_SECURE_NO_WARNINGS | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_SCL_SECURE_NO_DEPRECATE"
  - "_SCL_SECURE_NO_WARNINGS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_SCL_SECURE_NO_DEPRECATE"
  - "_SCL_SECURE_NO_WARNINGS"
ms.assetid: ef0ddea9-7c62-4b53-8b64-5f4fd369776f
caps.latest.revision: 5
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _SCL_SECURE_NO_WARNINGS
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Appeler des méthodes peuvent éventuellement non dans la bibliothèque C\+\+ standard provoque [Avertissement du compilateur \(niveau 3\) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md).  Pour désactiver cet avertissement, définissez macro **\_SCL\_SECURE\_NO\_WARNINGS** dans votre code :  
  
```  
#define _SCL_SECURE_NO_WARNINGS  
```  
  
## Notes  
 D'autres façons de désactiver C4996 d'avertissement sont les suivantes :  
  
-   À l'aide de le compilateur du [\/D \(Définitions de préprocesseur\)](../build/reference/d-preprocessor-definitions.md) :  
  
    ```  
    cl /D_SCL_SECURE_NO_WARNINGS [other compiler options] myfile.cpp  
    ```  
  
-   À l'aide de le compilateur de [\/w](../build/reference/compiler-option-warning-level.md) :  
  
    ```  
    cl /wd4996 [other compiler options] myfile.cpp  
    ```  
  
-   Utilisation de la directive d'[avertissement de \#pragma](../preprocessor/warning.md) :  
  
    ```  
    #pragma warning(disable:4996)  
    ```  
  
 En outre, vous pouvez modifier manuellement le niveau de C4996 avertissement avec l'option du compilateur d'**\/w\<l\>\<n\>**.  Par exemple, pour définir C4996 d'avertissement au niveau 4 :  
  
```  
cl /w44996 [other compiler options] myfile.cpp  
```  
  
 Pour plus d'informations, consultez [\/w, \/Wn, \/WX, \/Wall, \/wln, \/wdn, \/wen, \/won \(Niveau d'avertissement\)](../build/reference/compiler-option-warning-level.md).  
  
## Voir aussi  
 [Bibliothèques sécurisées : bibliothèque C\+\+ standard](../standard-library/safe-libraries-cpp-standard-library.md)