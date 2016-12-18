---
title: "Avertissement du compilateur (niveau 2) C4244 | Microsoft Docs"
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
  - "C4244"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4244"
ms.assetid: 2c19d157-21d1-42c2-a6c0-3f30f2ce3813
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 2) C4244
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'argument' : conversion de 'type1' en 'type2', perte possible de données  
  
 Un type à virgule flottante a été converti en type d'entier.  Une perte de données est possible.  
  
 Si l'erreur C4244 se produit, vous devez soit modifier votre programme pour utiliser des types compatibles, soit ajouter une certaine logique à votre code afin de garantir que la plage de valeurs possibles sera toujours compatible avec les types que vous utilisez.  
  
 L'avertissement C4244 peut également se déclencher aux niveaux 3 et 4 ; pour plus d'informations, consultez [Avertissement du compilateur \(niveaus 3 and 4\) C4244](../../error-messages/compiler-warnings/compiler-warning-levels-3-and-4-c4244.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C4244 :  
  
```  
// C4244_level2.cpp  
// compile with: /W2  
  
int f(int x){ return 0; }  
int main() {  
   double x = 10.1;  
   int i = 10;  
   return (f(x));   // C4244  
   // try the following line instead  
   // return (f(i));  
}  
```