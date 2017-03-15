---
title: "Tri partiel des mod&#232;les de fonction (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tri partiel des modèles de fonctions"
ms.assetid: 0c17347d-0e80-47ad-b5ac-046462d9dc73
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Tri partiel des mod&#232;les de fonction (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Plusieurs modèles de fonction qui correspondent à la liste d'arguments d'un appel de fonction peuvent être disponibles.  C\+\+ définit un classement partiel des modèles de fonction pour spécifier quelle fonction doit être appelée.  Le classement est partiel car certains modèles peuvent être considérés comme également spécialisés.  
  
 Le compilateur sélectionne la fonction de modèle la plus spécialisée disponible parmi les correspondances possibles.  Par exemple, si un modèle de fonction prend un type **T**, et qu'un autre modèle de fonction prenant **T\*** est disponible, la version **T\*** est considérée comme plus spécialisée et est préférée à la version **T** générique lorsque l'argument est un type pointeur, bien que les deux correspondances soient autorisées.  
  
 Utilisez le processus suivant pour déterminer si un candidat de modèle de fonction est plus spécialisé :  
  
1.  Considérez deux modèles de fonction, T1 et T2.  
  
2.  Remplacez les paramètres dans T1 par un type unique hypothétique X.  
  
3.  Avec la liste de paramètres dans T1, vérifiez si T2 est un modèle valide pour cette liste de paramètres.  Ignorez toutes les conversions implicites.  
  
4.  Répétez le même processus en inversant T1 et T2.  
  
5.  Si un modèle est une liste d'arguments template valide pour l'autre modèle, mais que l'inverse n'est pas vrai, ce modèle est considéré comme moins spécialisé que l'autre modèle.  Si les deux modèles utilisant l'étape précédente forment des arguments valides l'un pour l'autre, ils sont considérés comme également spécialisés et un appel ambigu se produit lorsque vous tentez de les utiliser.  
  
6.  Grâce à ces règles :  
  
    1.  Une spécialisation de modèle pour un type spécifique est plus spécialisée qu'une spécialisation acceptant un argument de type générique.  
  
    2.  Un modèle acceptant uniquement **T\*** est plus spécialisé qu'un modèle acceptant uniquement **T**, car un type hypothétique **X\*** est un argument valide pour un argument template **T**, mais **X** n'est pas un argument valide pour un argument template **T\***.  
  
    3.  **const T** est plus spécialisé que **T**, car **const X** est un argument valide pour un argument template **T**, mais **X** n'est pas un argument valide pour un argument template **const T**.  
  
    4.  **const T\*** est plus spécialisé que **T\***, car **const X\*** est un argument valide pour un argument template **T\***, mais **X\*** n'est pas un argument valide pour un argument template **const T\***.  
  
7.  L'exemple suivant s'applique à Visual C\+\+ .NET 2003, comme indiqué dans la norme :  
  
```  
// partial_ordering_of_function_templates.cpp  
// compile with: /EHsc  
#include <iostream>  
  
extern "C" int printf(const char*,...);  
template <class T> void f(T) {  
   printf_s("Less specialized function called\n");  
}  
  
template <class T> void f(T*) {  
   printf_s("More specialized function called\n");  
}  
  
template <class T> void f(const T*) {  
   printf_s("Even more specialized function for const T*\n");  
}  
  
int main() {  
   int i =0;  
   const int j = 0;  
   int *pi = &i;  
   const int *cpi = &j;  
  
   f(i);   // Calls less specialized function.  
   f(pi);  // Calls more specialized function.  
   f(cpi); // Calls even more specialized function.  
   // Without partial ordering, these calls would be ambiguous.  
}  
```  
  
### Sortie  
  
```  
Less specialized function called  
More specialized function called  
Even more specialized function for const T*  
```  
  
## Voir aussi  
 [Modèles de fonctions](../cpp/function-templates.md)