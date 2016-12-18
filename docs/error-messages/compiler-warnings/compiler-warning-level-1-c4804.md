---
title: "Avertissement du compilateur (niveau 1) C4804 | Microsoft Docs"
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
  - "C4804"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4804"
ms.assetid: 069e8f44-3ef6-43bb-8524-4116fc6eea83
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4804
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'opération' : utilisation risquée du type 'bool' dans l'opération  
  
 Cet avertissement se produit lorsque vous utilisez une variable ou une valeur `bool` de manière inattendue.  C4804 est généré, par exemple, si vous utilisez des opérateurs tels que l'opérateur unaire négatif \(**\-**\) ou l'opérateur de complément \(`~`\).  Le compilateur évalue l'expression.  
  
## Exemple  
 L'exemple suivant génère l'erreur C4804 :  
  
```  
// C4804.cpp  
// compile with: /W1  
  
int main()  
{  
   bool i = true;  
   if (-i)   // C4804, remove the '-' to resolve  
   {  
      i = false;  
   }  
}  
```