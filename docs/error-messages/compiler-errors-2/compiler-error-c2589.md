---
title: "Erreur du compilateur C2589 | Microsoft Docs"
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
  - "C2589"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2589"
ms.assetid: 1d7942c7-8a81-4bb4-b272-76a0019e8513
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2589
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : jeton non conforme à droite de '::'  
  
 Si un nom de classe, de structure ou d'union apparaît à gauche de l'opérateur de résolution de portée \(::\), le jeton à droite doit être un membre de classe, de structure ou d'union.  Sinon, tout identificateur global peut apparaître sur la droite.  
  
 L'opérateur de résolution de portée ne peut pas être surchargé.  
  
 L'exemple suivant génère l'erreur C2589 :  
  
```  
// C2589.cpp  
void Test(){}  
class A {};  
void operator :: ();   // C2589  
  
int main() {  
   ::Test();  
}  
```