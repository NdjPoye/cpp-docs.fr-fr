---
title: "Avertissement du compilateur (niveau 1) C4744 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4744"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4744"
ms.assetid: f2a7d0b5-afd5-4926-abc3-cfbd367e3ff5
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Avertissement du compilateur (niveau 1) C4744
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' a un type différent dans 'fichier1' et 'fichier2' : 'type1'' et 'type2'  
  
 Une variable externe référencée ou définie dans deux fichiers possède des types différents dans ceux\-ci.  Pour remédier à cela, rendez les définitions de type identiques ou modifiez le nom de la variable dans l'un des fichiers.  
  
 L'erreur C4744 est émise uniquement lorsque les fichiers sont compilés avec \/GL.  Pour plus d'informations, consultez [\/GL \(Optimisation de l'ensemble du programme\)](../../build/reference/gl-whole-program-optimization.md).  
  
> [!NOTE]
>  L'erreur C4744 se produit généralement dans les fichiers C \(pas C\+\+\), car en C\+\+, un nom de variable est décoré avec les informations de type.  Lorsque l'exemple \(ci\-dessous\) est compilé en tant que C\+\+, l'erreur de l'éditeur de liens LNK2019 est générée.  
  
## Exemple  
 Cet exemple contient la première définition.  
  
```  
// C4744.c  
// compile with: /c /GL  
int global;  
```  
  
## Exemple  
 L'exemple suivant génère l'erreur C4744 :  
  
```  
// C4744b.c  
// compile with: C4744.c /GL /W1  
// C4744 expected  
#include <stdio.h>  
  
extern unsigned global;  
  
main()   
{  
    printf_s("%d\n", global);  
}  
```