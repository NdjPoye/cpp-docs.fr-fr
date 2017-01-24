---
title: "Avertissement du compilateur (niveau 1) C4731 | Microsoft Docs"
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
  - "C4731"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4731"
ms.assetid: 5658c24c-3e6f-4505-835b-1fb92d47cab0
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4731
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'pointeur' : registre de pointeur frame 'registre' modifié par le code assembleur inline  
  
 Le registre d'un pointeur frame a été modifié.  Vous devez enregistrer et restaurer le registre dans votre variable bloc ou frame d'assembly inline \(local ou paramètre, suivant le registre modifié\), sinon votre code risque de ne pas fonctionner correctement.  
  
 L'exemple suivant génère l'erreur C4731 :  
  
```  
// C4731.cpp  
// compile with: /W1 /LD  
// processor: x86  
// C4731 expected  
void bad(int p) {  
   __asm  
   {  
      mov ebp, 1  
   }  
  
   if (p == 1)  
   {  
      // ...  
   }  
}  
```  
  
 EBP est le pointeur frame \(FPO est interdit\) et il est modifié.  Lorsque `p` est ensuite référencé, il l'est par rapport à `EBP`.  Mais `EBP` a été remplacé par le code, le programme ne fonctionnera donc pas correctement et peut même défaillir.