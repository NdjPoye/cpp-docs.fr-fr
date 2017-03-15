---
title: "Avertissement du compilateur (niveau 2) C4307 | Microsoft Docs"
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
  - "C4307"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4307"
ms.assetid: 7cca11e9-be61-49e4-8b15-88b84f0cbf07
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 2) C4307
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'opérateur' : dépassement de constante intégrale  
  
 L'opérateur est utilisé dans une expression qui entraîne le débordement par une constante entière de l'espace qui lui est alloué.  Il peut être nécessaire d'utiliser un type de taille supérieure pour la constante.  Un type **signed int** peut contenir des valeurs plus petites que `unsigned int` parce que le **signed int** utilise un bit pour représenter le signe.  
  
 L'exemple suivant génère l'erreur C4307 :  
  
```  
// C4307.cpp  
// compile with: /W2  
int i = 2000000000 + 2000000000;   // C4307  
int j = (unsigned)2000000000 + 2000000000;   // OK  
  
int main()  
{  
}  
```