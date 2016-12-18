---
title: "Fonctions non prototyp&#233;es | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 34200b8c-5b52-4f0d-aff8-9f70d82868ed
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Fonctions non prototyp&#233;es
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour les fonctions qui ne sont pas complètement prototypées, l'appelant passe les valeurs entières en tant qu'entiers et les valeurs à virgule flottante en tant que double précision.  Pour les valeurs à virgule flottante uniquement, le registre entier et le registre à virgule flottante contiendra la valeur float si l'appelé attend cette valeur dans les registres entiers.  
  
```  
func1();  
func2() {   // RCX = 2, RDX = XMM1 = 1.0, and R8 = 7  
   func1(2, 1.0, 7);  
}  
```  
  
## Voir aussi  
 [Convention d'appel](../build/calling-convention.md)