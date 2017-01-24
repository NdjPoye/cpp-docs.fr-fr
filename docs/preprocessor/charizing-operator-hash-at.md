---
title: "Op&#233;rateur charizing (#@) | Microsoft Docs"
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
  - "#@"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#@ (opérateur de préprocesseur)"
  - "charizing (opérateur)"
  - "préprocesseur, opérateurs"
ms.assetid: dee03314-d27c-4063-965c-64756efbef22
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Op&#233;rateur charizing (#@)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 L'opérateur charizing peut être utilisé uniquement avec des arguments de macros.  Si **\#@** précède un paramètre formel dans la définition de la macro, l'argument réel est placé entre guillemets simples et traité comme un caractère lorsque la macro est développée.  Par exemple :  
  
```  
#define makechar(x)  #@x  
```  
  
 provoque le développement de l'instruction  
  
```  
a = makechar(b);  
```  
  
 en  
  
```  
a = 'b';  
```  
  
 Le guillemet simple ne peut pas être utilisé avec l'opérateur charizing.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Opérateurs de préprocesseur](../preprocessor/preprocessor-operators.md)