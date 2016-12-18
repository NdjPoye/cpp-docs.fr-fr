---
title: "L&#39;utilisation d&#39;un nom de fonction sans () ne g&#233;n&#232;re pas de code | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fonctions (C++), sans parenthèses"
ms.assetid: edf4a177-a160-44aa-8436-e077b5b27809
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# L&#39;utilisation d&#39;un nom de fonction sans () ne g&#233;n&#232;re pas de code
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Quand un nom de fonction déclaré dans votre programme est utilisé sans parenthèses, le compilateur ne génère pas de code.  Cette situation se produit pour que la fonction prenne des paramètres ou non car le compilateur calcule l'adresse de la fonction ; cependant, dans la mesure où l'opérateur de l'appel de fonction "\(\)" n'est pas présent, aucun appel n'a lieu.  Ce résultat est similaire au texte suivant :  
  
```  
// compile with /Wall to generate a warning  
int a;  
a;      // no code generated here either  
```  
  
 Dans Visual C\+\+, même l'utilisation d'un avertissement de niveau 4 ne produit pas une sortie de diagnostic.  Aucun avertissement n'est émis ; aucun code n'est généré.  
  
 L'exemple de code ci\-dessous est compilé \(avec un avertissement\) et lié correctement, sans erreur, mais ne produit pas de code en référence à `funcn( )`.  Pour que ceci fonctionne correctement, ajoutez l'opérateur d'appel de fonction "\(\)".  
  
```  
#include <stdio.h>  
void funcn();  
  
int main() {  
   funcn;      /* missing function call operator;   
                  call will fail.  Use funcn() */  
   }  
  
void funcn() {  
   printf("\nHello World\n");  
}  
```  
  
## Voir aussi  
 [Optimisation du code](../../build/reference/optimizing-your-code.md)