---
title: "Avertissement du compilateur (niveau 3) C4995 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4995"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4995"
ms.assetid: c6b61755-4730-4947-ad4d-d1c2bc82585a
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Avertissement du compilateur (niveau 3) C4995
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : le nom a été marqué comme \#pragma deprecated  
  
 Le compilateur a rencontré une fonction qui était marquée avec le pragma [deprecated](../../preprocessor/deprecated-c-cpp.md).  La fonction ne sera peut\-être plus prise en charge dans une future version.  Vous pouvez désactiver cet avertissement avec le pragma [warning](../../preprocessor/warning.md) \(exemple ci\-dessous\).  
  
## Exemple  
 L'exemple suivant génère l'erreur C4995 :  
  
```  
// C4995.cpp  
// compile with: /W3  
#include <stdio.h>  
  
// #pragma warning(disable : 4995)  
void func1(void)  
{  
    printf("\nIn func1");  
}  
  
int main()   
{  
    func1();  
    #pragma deprecated(func1)  
    func1();   // C4995  
}  
```