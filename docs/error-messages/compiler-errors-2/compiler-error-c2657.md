---
title: "Erreur du compilateur C2657 | Microsoft Docs"
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
  - "C2657"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2657"
ms.assetid: f7cf29a9-684a-4605-9469-ecfee9ba4b03
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2657
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe::\*' trouvé\(e\) en début d'instruction \(n'auriez\-vous pas oublié de spécifier un type ?\)  
  
 La ligne commence par un identificateur pointeur vers membre.  
  
 Cette erreur peut être provoquée par un spécificateur de type manquant dans la déclaration d'un pointeur vers un membre.  
  
 L'exemple suivant génère l'erreur C2657 :  
  
```  
// C2657.cpp  
class C {};  
int main() {  
   C::* pmc1;        // C2657  
   int C::* pmc2;   // OK  
}  
```