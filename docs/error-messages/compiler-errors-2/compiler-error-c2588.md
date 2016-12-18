---
title: "Erreur du compilateur C2588 | Microsoft Docs"
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
  - "C2588"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2588"
ms.assetid: 19a0cabd-ca13-44a5-9be3-ee676abf9bc4
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2588
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'::~identificateur' : destructeur global non conforme  
  
 Le destructeur est défini pour un élément autre qu'une classe, une structure ou une union.  Cela n'est pas autorisé.  
  
 Cette erreur peut être provoquée par un nom de classe, de structure ou d'union manquant dans la partie gauche de l'opérateur de résolution de portée \(`::`\).  
  
 L'exemple suivant génère l'erreur C2588 :  
  
```  
// C2588.cpp  
~F();   // C2588  
```