---
title: "Erreur irr&#233;cup&#233;rable C1311 | Microsoft Docs"
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
  - "C1311"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1311"
ms.assetid: 6590a06c-ce9d-4f17-8f62-c809343143b8
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable C1311
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le format COFF ne peut pas initialiser de manière statique 'var' avec 'nombre' octet\(s\) d'une adresse  
  
 Une adresse dont la valeur n'est pas connue au moment de la compilation ne peut pas être assignée de manière statique à une variable dont le type possède un stockage inférieur à quatre octets.  
  
 Cette erreur peut se produire sur du code qui est normalement du code C\+\+ valide.  
  
 L'exemple de code suivant illustre une condition pouvant générer l'erreur C1311.  
  
```  
char c = (char)"Hello, world";   // C1311  
char *d = (char*)"Hello, world";   // OK  
```