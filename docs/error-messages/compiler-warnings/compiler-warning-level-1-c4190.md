---
title: "Avertissement du compilateur (niveau 1) C4190 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4190"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4190"
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement du compilateur (niveau 1) C4190
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur1' a une liaison C spécifiée, mais retourne 'identificateur2' UDT qui est incompatible avec C  
  
 Une fonction ou un pointeur vers une fonction a un type défini par l'utilisateur ou UDT \(User\-Defined Type, classe, structure, enum, union ou [\_\_value](../../misc/value.md)\) comme type de retour et une liaison `extern` "C".  Ceci est autorisé si :  
  
-   Tous les appels à cette fonction sont effectués depuis C\+\+.  
  
-   La définition de la fonction est en C\+\+.  
  
## Exemple  
  
```  
// C4190.cpp  
// compile with: /W1 /LD  
struct X  
{  
   int i;  
   X ();  
   virtual ~X ();  
};  
  
extern "C" X func ();   // C4190  
```