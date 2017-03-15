---
title: "Erreur du compilateur C2803 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2803"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2803"
ms.assetid: 2cdbe374-8cc4-4c4e-ba15-062a7479e937
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C2803
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator opérateur' doit avoir au moins un paramètre de type classe  
  
 L'opérateur surchargé ne possède pas de paramètre de type classe.  
  
 Vous devez passer au moins un paramètre par référence \(sans utiliser de pointeurs, mais plutôt des références\) ou par valeur pour pouvoir écrire "a \< b" \(a et b étant de type classe A\).  
  
 Si les deux paramètres sont des pointeurs, il s'agira d'une pure comparaison d'adresses de pointeur qui n'utilisera pas la conversion définie par l'utilisateur.  
  
 L'exemple suivant génère l'erreur C2803 :  
  
```  
// C2803.cpp  
// compile with: /c  
class A{};  
bool operator< (const A *left, const A *right);   // C2803  
// try the following line instead  
// bool operator< (const A& left, const A& right);  
```