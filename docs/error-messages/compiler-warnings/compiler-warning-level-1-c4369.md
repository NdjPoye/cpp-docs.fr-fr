---
title: "Avertissement du compilateur (niveau 1) C4369 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4369"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4369"
ms.assetid: ade87e84-36be-4e00-be99-2930af848feb
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement du compilateur (niveau 1) C4369
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'énumérateur' : la valeur de l'énumérateur 'valeur' ne peut pas être représentée sous la forme 'type', la valeur est 'nouvelle\_valeur'  
  
 Un énumérateur a été calculé comme supérieur à la plus grande valeur du type sous\-jacent spécifié.  Cela est dû à un dépassement de capacité et le compilateur a encapsulé la valeur de l'énumérateur dans la plus faible valeur possible pour le type.  
  
## Exemple  
 L'exemple suivant génère l'erreur C4369 :  
  
```  
// C4369.cpp  
// compile with: /W1  
int main() {  
   enum Color: char { red = 0x7e, green, blue };   // C4369  
   enum Color2: char { red2 = 0x7d, green2, blue2};   // OK  
}  
```