---
title: "Erreur du compilateur C3530 | Microsoft Docs"
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
  - "C3530"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3530"
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3530
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

« auto » ne peut pas être combiné avec un autre spécificateur de type  
  
 Un spécificateur de type est utilisé avec le mot clé `auto`.  
  
### Pour corriger cette erreur  
  
1.  N'utilisez pas de spécificateur de type dans une déclaration de variable qui utilise le mot clé `auto`.  
  
## Exemple  
 L'exemple suivant donne C3530 parce que la variable `x` est déclaré avec le mot clé `int` et le type `auto`, et parce que l'exemple est compilé avec **\/Zc:auto**.  
  
```  
// C3530.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto int x;   // C3530  
   return 0;  
}  
```  
  
## Voir aussi  
 [auto, mot clé](../../cpp/auto-keyword.md)