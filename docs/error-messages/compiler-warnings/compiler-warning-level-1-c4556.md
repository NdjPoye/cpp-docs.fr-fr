---
title: "Avertissement du compilateur (niveau 1) C4556 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "xml"
  - "C4556"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4556"
ms.assetid: e4c0e296-b747-4db1-9608-30b8b74feac2
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement du compilateur (niveau 1) C4556
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

valeur d'argument immédiat intrinsèque 'valeur' hors limites 'LimiteInférieure \- LimiteSupérieure'  
  
 Une valeur intrinsèque correspond à une instruction matérielle.  L'instruction matérielle a un nombre de bits fixe pour encoder la constante.  Si ***valeur*** est en dehors des limites, elle ne sera pas encodée correctement.  Le compilateur tronque les bits supplémentaires.  
  
 L'exemple suivant génère l'erreur C4556 :  
  
```  
// C4556.cpp  
// compile with: /W1  
// processor: x86 IPF  
#include <xmmintrin.h>  
void test()  
{  
   __m64 m;  
   _m_pextrw(m, 5);   // C4556  
}  
int main()  
{  
}  
```