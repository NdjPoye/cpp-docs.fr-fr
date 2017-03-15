---
title: "Erreur du compilateur C2467 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2467"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2467"
ms.assetid: f9ead270-5d0b-41cc-bdcd-586a647c67a7
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C2467
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

déclaration de 'type\-défini\-par\-utilisateur' anonyme non conforme  
  
 Un type imbriqué défini par l'utilisateur a été déclaré.  Cette erreur se produit lors de la compilation du code source en C avec l'option de compatibilité ANSI \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) activée.  
  
 L'exemple suivant génère l'erreur C2467 :  
  
```  
//C2467.c  
// compile with: /Za   
int main() {  
   struct X {  
      union { int i; };   // C2467, nested declaration  
   };  
}  
```