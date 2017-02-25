---
title: "Exemple d&#39;appel&#160;: prototype de fonction et appel | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "conventions d'appel, exemples (C++)"
  - "exemples (C++), conventions d'appel"
ms.assetid: e4275d1f-df2e-4bfc-a162-eb43ec69554a
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Exemple d&#39;appel&#160;: prototype de fonction et appel
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Section spécifique à Microsoft  
 L'exemple suivant montre les résultats d'un appel de fonction effectué à l'aide de différentes conventions d'appel.  
  
 Cet exemple repose sur la structure de fonction suivante.  Remplacez `calltype` par la convention d'appel appropriée.  
  
```  
void    calltype MyFunc( char c, short s, int i, double f );  
.  
.  
.  
void    MyFunc( char c, short s, int i, double f )  
    {  
    .  
    .  
    .  
    }  
.  
.  
.  
MyFunc ('x', 12, 8192, 2.7183);  
```  
  
 Pour plus d'informations, consultez [Exemple de résultats d'appel](../cpp/results-of-calling-example.md).  
  
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [Conventions d'appel](../cpp/calling-conventions.md)