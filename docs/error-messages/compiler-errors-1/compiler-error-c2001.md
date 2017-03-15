---
title: "Erreur du compilateur C2001 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2001"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2001"
ms.assetid: 0c3a7821-d8e5-4398-ab5a-4116d46e8dda
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C2001
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

saut de ligne dans la constante  
  
 Une constante chaîne ne peut se poursuivre sur une deuxième ligne, sauf si vous :  
  
-   terminez la première ligne par une barre oblique inverse ;  
  
-   fermez la chaîne sur la première ligne par un guillemet double, pour la rouvrir sur la ligne suivante avec un autre guillemet double.  
  
 Il ne suffit pas de terminer la première ligne par \\n.  
  
## Exemple  
 L'exemple suivant génère l'erreur C2001 :  
  
```  
// C2001.cpp  
// C2001 expected  
#include <stdio.h>  
  
int main()  
{  
    printf_s("Hello,  
             world");  
    printf_s("Hello,\n  
             world");  
}  
```  
  
## Exemple  
 Les espaces au début de la ligne suivante après un caractère de continuation de ligne sont inclus dans la constante chaîne.  Aucun des exemples ci\-dessus n'incorpore de caractère de saut de ligne dans la constante chaîne.  Vous pouvez incorporer un caractère de saut de ligne comme indiqué ci\-dessous :  
  
```  
// C2001b.cpp  
#include <stdio.h>  
  
int main()  
{  
    printf_s("Hello,\n\  
             world");  
  
    printf_s("Hello,\  
             \nworld");  
  
    printf_s("Hello,\n"  
             "world");  
  
    printf_s("Hello,"  
             "\nworld");  
  
    printf_s("Hello,"  
             " world");  
  
    printf_s("Hello,\  
             world");  
}  
```