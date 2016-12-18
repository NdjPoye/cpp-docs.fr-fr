---
title: "num&#233;riques (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "<cliext/numeric>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "en-tête <cliext/numeric> (STL/CLR)"
  - "en-tête <numeric> (STL/CLR)"
  - "fonctions numériques (STL/CLR)"
ms.assetid: 1dc4d9a3-e734-459c-9678-5d9be0ef4c79
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# num&#233;riques (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit les fonctions de modèle de conteneur qui exécutent des algorithmes pour le traitement numérique.  
  
## Syntaxe  
  
```  
#include <cliext/numeric>  
```  
  
## Fonctions  
  
|Fonction|Description|  
|--------------|-----------------|  
|[accumulate](../dotnet/accumulate-stl-clr.md)|Calcule la somme de tous les éléments dans une plage spécifiée incluant une valeur initiale en calculant les sommes partielles consécutives, ou calcule le résultat de résultats partiels consécutifs obtenus en utilisant une opération binaire spécifiée autre que la somme.|  
|[adjacent\_difference](../dotnet/adjacent-difference-stl-clr.md)|Détermine les différences successives entre chaque élément et son prédécesseur au sein d'une plage d'entrée, puis génère les résultats dans une plage de destination ou calcule le résultat d'une procédure généralisée dans laquelle l'opération de différence est remplacée par une autre opération binaire spécifiée.|  
|[inner\_product](../dotnet/inner-product-stl-clr.md)|Calcule la somme du produit selon l'élément de plusieurs plages et l'ajoute à une valeur initiale spécifiée ou calcule le résultat d'une procédure généralisée où les opérations de somme et de produit binaire sont remplacées par d'autres opérations binaire spécifiées.|  
|[partial\_sum](../dotnet/partial-sum-stl-clr.md)|Calcule une série de sommes dans une plage d'entrée depuis le premier élément jusqu'à l'élément numéro `i`, puis stocke le résultat de chaque somme dans l'élément numéro `i` d'une plage de destination, ou calcule le résultat d'une procédure généralisée où l'opération de somme est remplacée par une autre opération binaire spécifiée.|  
  
## Configuration requise  
 **En\-tête:** \<cliext\/numeric\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [STL\/CLR, bibliothèque](../dotnet/stl-clr-library-reference.md)