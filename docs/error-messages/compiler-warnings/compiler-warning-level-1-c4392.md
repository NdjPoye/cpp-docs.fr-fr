---
title: "Avertissement du compilateur (niveau 1) C4392 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4392"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4392"
ms.assetid: 817806ad-06a6-4b9e-8355-e25687c782dc
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement du compilateur (niveau 1) C4392
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'signature' : nombre d'arguments incorrect pour la fonction intrinsèque, 'nombre' arguments attendus  
  
 Une déclaration de fonction pour une fonction intrinsèque du compilateur avait un nombre d'arguments incorrect.  L'image résultante peut ne pas s'exécuter correctement.  
  
 Pour résoudre cet avertissement, vous pouvez soit corriger la déclaration, soit supprimer la déclaration et vous contenter d'inclure le fichier d'en\-tête approprié par \#include.  
  
 L'exemple suivant génère l'erreur C4392 :  
  
```  
// C4392.cpp  
// compile with: /W1  
// processor: x86  
// uncomment the following line and delete the line that  
// generated the warning to resolve  
// #include "xmmintrin.h"  
  
#ifdef  __cplusplus  
extern "C" {  
#endif  
  
extern void _mm_stream_pd(double *dp);   // C4392  
  
#ifdef  __cplusplus  
}  
#endif  
  
int main()  
{  
}  
```