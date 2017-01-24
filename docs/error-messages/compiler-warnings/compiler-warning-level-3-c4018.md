---
title: "Avertissement du compilateur (niveau 3) C4018 | Microsoft Docs"
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
  - "C4018"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4018"
ms.assetid: 6e8cbb04-d914-4319-b431-cbc2fbe40eb1
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 3) C4018
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'expression' : incompatibilité signed\/unsigned  
  
 La comparaison d'un nombre signé avec un nombre non signé requiert que le compilateur convertisse la valeur signée en valeur non signée.  
  
 Cet avertissement peut être résolu en castant un des deux types lors du test des types signed et unsigned.  
  
 L'exemple suivant génère l'erreur C4018 :  
  
```  
// C4018.cpp  
// compile with: /W3  
int main() {  
   unsigned int uc = 0;  
   int c = 0;  
   unsigned int c2 = 0;  
  
   if (uc < c) uc = 0;   // C4018  
  
   // OK  
   if (uc == c2) uc = 0;  
}  
```