---
title: "Avertissement du compilateur (niveau&#160;1) C4807 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4807"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4807"
ms.assetid: 089c9f87-fd81-402e-9826-66a8ef1ef1fe
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1) C4807
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operation' : mélange risqué de type 'type' et champ de bits signé de type 'type'  
  
 Cet avertissement est généré lors de la comparaison d’un champ de bits signé à un bit avec une variable `bool`. Un champ de bits signé à un bit peut seulement contenir les valeurs \-1 ou 0. Il est risqué de le comparer à `bool`. Aucun avertissement n’est généré sur la combinaison de `bool` et de champs de bits non signés à un bit, car ils sont identiques à `bool` et ne peuvent contenir que 0 ou 1.  
  
## Exemple  
 L’exemple suivant génère l’erreur C4807 :  
  
```  
// C4807.cpp // compile with: /W1 typedef struct bitfield { signed mybit : 1; } mybitfield; int main() { mybitfield bf; bool b = true; // try.. // int b = true; bf.mybit = -1; if (b == bf.mybit) {   // C4807 b = false; } }  
```