---
title: "Erreur du compilateur C2457 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2457"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2457"
ms.assetid: 347e169d-23ad-434f-8836-5b09b53980ff
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2457
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'macro' : une macro prédéfinie ne peut pas apparaître à l'extérieur du corps d'une fonction  
  
 Vous avez tenté d'utiliser une macro prédéfinie, telle que [\_\_FUNCTION\_\_](../../preprocessor/predefined-macros.md), dans un espace global.  
  
## Exemple  
 L'exemple suivant génère l'erreur C2457 :  
  
```  
// C2457.cpp  
#include <stdio.h>  
  
__FUNCTION__;   // C2457, cannot be global  
  
int main()   
{  
    printf_s("\n%s",__FUNCTION__);   // OK  
}  
```