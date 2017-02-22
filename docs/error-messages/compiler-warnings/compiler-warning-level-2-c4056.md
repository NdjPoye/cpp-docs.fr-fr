---
title: "Avertissement du compilateur (niveau 2) C4056 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4056"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4056"
ms.assetid: a3c3a9b8-ec30-452d-96cb-3694adcce789
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement du compilateur (niveau 2) C4056
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

débordement d'une opération arithmétique de constante à virgule flottante  
  
 Une opération arithmétique de constante à virgule flottante génère un résultat qui dépasse la valeur maximale autorisée.  
  
 Cet avertissement peut être provoqué par l'exécution d'optimisations du compilateur pendant une opération arithmétique constante.  Vous pouvez ignorer cet avertissement en toute sécurité s'il disparaît en désactivant l'optimisation \([\/Od](../../build/reference/od-disable-debug.md)\).  
  
 L'exemple suivant génère l'erreur C4056 :  
  
```  
// C4056.cpp  
// compile with: /W2 /LD  
#pragma warning (default : 4056)  
float fp_val = 1.0e300 * 1.0e300;   // C4056  
```