---
title: "Avertissement du compilateur (niveau 1) C4142 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4142"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4142"
ms.assetid: 1fdfc3dc-60a2-4f00-b133-20e400f9b7a6
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement du compilateur (niveau 1) C4142
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

redéfinition bénigne du type  
  
 Un type est redéfini d'une façon qui n'a aucun effet sur le code généré.  
  
 Pour résoudre le problème en vérifiant les causes possibles suivantes :  
  
-   Une fonction membre ou une classe dérivée a un type de retour différent de la fonction membre correspondante de la classe de base.  
  
-   Un type défini avec la commande `typedef` est redéfini avec une syntaxe différente.  
  
 L'exemple suivant génère l'erreur C4142 :  
  
```  
// C4142.c  
// compile with: /W1  
float X2;  
X2 = 2.0 + 1.0;   // C4142  
  
int main() {  
   float X2;  
   X2 = 2.0 + 1.0;   // OK  
}  
```