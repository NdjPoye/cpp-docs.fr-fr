---
title: "Erreur du compilateur C2712 | Microsoft Docs"
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
  - "C2712"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2712"
ms.assetid: f7d4ffcc-7ed2-459b-8067-a728ce647071
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2712
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible d'utiliser \_\_try dans les fonctions nécessitant un déroulement d'objet  
  
 L'erreur C2712 peut se produire si vous utilisez [\/EHsc](../../build/reference/eh-exception-handling-model.md) et qu'une fonction avec la gestion structurée des exceptions possède également des objets nécessitant un déroulement \(destruction\).  
  
 Solutions possibles :  
  
-   Déplacez le code nécessitant la gestion structurée des exceptions vers une autre fonction.  
  
-   Réécrivez les fonctions qui utilisent la gestion structurée des exceptions pour éviter l'utilisation de variables locales et de paramètres possédant des destructeurs.  N'utilisez pas la gestion structurée des exceptions dans les constructeurs ni les destructeurs.  
  
-   Compilez sans \/EHsc.  
  
 L'erreur C2712 peut également se produire si vous appelez une méthode déclarée à l'aide du mot clé [\_\_event](../../cpp/event.md).  Comme l'événement peut être utilisé dans un environnement multithread, le compilateur génère du code qui empêche toute manipulation de l'objet événement sous\-jacent, puis place le code généré dans une [instruction try\-finally](../../cpp/try-finally-statement.md) de gestion structurée des exceptions.  Par conséquent, l'erreur C2712 se produit si vous appelez la méthode d'événement et passez par valeur un argument dont le type possède un destructeur.  Dans ce cas, une solution consiste à passer l'argument en tant que référence constante.  
  
## Exemple  
 L'erreur C2712 peut également se produire si vous compilez avec **\/clr:pure** et déclarez un tableau statique de pointeurs vers des fonctions dans un bloc `__try`.  Un membre statique exige du compilateur qu'il utilise l'initialisation dynamique sous **\/clr:pure**, ce qui implique la gestion des exceptions C\+\+.  Toutefois, la gestion des exceptions C\+\+ n'est pas autorisée dans un bloc `__try`.  
  
 L'exemple suivant génère l'erreur C2712 et montre comment la corriger.  
  
```  
// C2712.cpp  
// compile with: /clr:pure /c  
struct S1 {  
   static int smf();  
   void fnc();  
};  
  
void S1::fnc() {  
   __try {  
      static int (*array_1[])() = {smf,};   // C2712  
  
      // OK  
      static int (*array_2[2])();  
      array_2[0] = smf;  
    }  
    __except(0) {}  
}  
```