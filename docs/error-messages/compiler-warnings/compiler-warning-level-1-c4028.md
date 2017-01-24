---
title: "Avertissement du compilateur (niveau 1) C4028 | Microsoft Docs"
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
  - "C4028"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4028"
ms.assetid: c3e8b70b-e870-416c-a285-bba5f71dbfc6
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4028
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

paramètre formel 'numéro' différent de la déclaration  
  
 Le type du paramètre formel ne correspond pas au paramètre correspondant dans la déclaration.  Le type de la déclaration d'origine est utilisé.  
  
 Cet avertissement n'est valide que pour le code source C.  
  
## Exemple  
 L'exemple suivant génère l'erreur C4028 :  
  
```  
// C4028.c  
// compile with: /W1 /Za  
void f(int , ...);  
void f(int i, int j) {}   // C4028  
  
void g(int , int);  
void g(int i, int j) {}   // OK  
  
int main() {}  
```