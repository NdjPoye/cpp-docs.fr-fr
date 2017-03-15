---
title: "Erreur du compilateur C2449 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2449"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2449"
ms.assetid: 544bf0b6-daa0-40e8-9f21-8e583d472a2d
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C2449
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

trouvé '{' au niveau de la portée du fichier \(en\-tête de fonction manquant ?\)  
  
 Une accolade ouvrante apparaît au niveau de la portée du fichier.  
  
 Cette erreur peut être générée en présence d'un point\-virgule entre un en\-tête de fonction et l'accolade ouvrante de la définition de fonction.  
  
 L'exemple suivant génère l'erreur C2499 :  
  
```  
// C2449.c  
// compile with: /c  
void __stdcall func(void) {}   // OK  
void __stdcall func(void);  // extra semicolon on this line  
{                         // C2449 detected here  
```