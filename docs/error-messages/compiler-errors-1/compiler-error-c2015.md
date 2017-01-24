---
title: "Erreur du compilateur C2015 | Microsoft Docs"
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
  - "C2015"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2015"
ms.assetid: 8f40af0a-3a5a-4d6a-8ed7-125966e6bfed
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2015
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

trop de caractères dans la constante  
  
 Une constante caractère contient plus de deux caractères.  La limite est d'un caractère pour les constantes caractère standard et deux caractères pour les constantes caractère long.  
  
 Une séquence d'échappement, telle que \\t, est convertie en un seul caractère.  
  
## Exemple  
 L'exemple suivant génère l'erreur C2015 :  
  
```  
// C2015.cpp  
// compile with: /c  
  
char test1 = 'error';   // C2015  
char test2 = 'e';   // OK  
```  
  
## Exemple  
 L'erreur C2015 peut également se produire en cas d'utilisation d'une extension Microsoft, constantes caractère converties en entiers.  L'exemple suivant génère l'erreur C2015 :  
  
```  
// C2015b.cpp  
#include <stdio.h>  
  
int main()   
{  
    int a = 'abcde';   // C2015  
  
    int b = 'a';   // 'a' = ascii 0x61  
    printf_s("%x\n", b);  
}  
```