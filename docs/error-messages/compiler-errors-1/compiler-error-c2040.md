---
title: "Erreur du compilateur C2040 | Microsoft Docs"
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
  - "C2040"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2040"
ms.assetid: 74ca3592-1469-4965-ab34-a4815e2fbefe
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2040
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'opérateur' : les niveaux d'indirection de 'identificateur1' et de 'identificateur2' sont différents  
  
 Une expression impliquant les opérandes spécifiés possède des types d'opérande incompatibles ou convertis implicitement.  Si les deux opérandes sont arithmétiques ou si les deux sont non arithmétiques \(tels qu'un tableau ou un pointeur\), ils sont utilisés sans modification.  Si un opérande est arithmétique et que l'autre ne l'est pas, l'opérande arithmétique est converti vers le type de l'opérande non arithmétique.  
  
 Cet exemple génère l'erreur C2040 et montre comment la corriger.  
  
```  
// C2040.cpp  
// Compile by using: cl /c /W3 C2040.cpp  
bool test() {  
   char c = '3';  
   return c == "3"; // C2446, C2040  
   // return c == '3'; // OK  
}  
  
```