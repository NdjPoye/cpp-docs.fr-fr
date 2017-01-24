---
title: "Erreur du compilateur C2562 | Microsoft Docs"
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
  - "C2562"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2562"
ms.assetid: 2c41e511-9952-4b98-9976-6b1523613e1b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2562
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : fonction 'void' retournant une valeur  
  
 La fonction est déclarée comme `void` mais retourne une valeur.  
  
 Cette erreur peut être provoquée par un prototype de fonction incorrect.  
  
 Cette erreur peut être résolue si vous spécifiez le type de retour dans la déclaration de fonction.  
  
 L'exemple suivant génère l'erreur C2562 :  
  
```  
// C2562.cpp  
// compile with: /c  
void testfunc() {  
   int i;  
   return i;   // C2562 delete the return to resolve  
}  
```