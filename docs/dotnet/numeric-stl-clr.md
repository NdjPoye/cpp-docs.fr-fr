---
title: "numérique (STL/CLR) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: <cliext/numeric>
dev_langs: C++
helpviewer_keywords:
- numeric functions [STL/CLR]
- <cliext/numeric> header [STL/CLR]
- <numeric> header [STL/CLR]
ms.assetid: 1dc4d9a3-e734-459c-9678-5d9be0ef4c79
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: cdf9ccb65299af688fde2fbff7b3d6cedad6de96
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="numeric-stlclr"></a>numériques (STL/CLR)
Définit les fonctions de modèle de conteneur qui exécutent des algorithmes fournis pour le traitement numérique.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
#include <cliext/numeric>  
```  
  
## <a name="functions"></a>Fonctions  
  
|Fonction|Description|  
|--------------|-----------------|  
|[accumulate (STL/CLR)](../dotnet/accumulate-stl-clr.md)|Calcule la somme de tous les éléments d’une plage spécifiée incluant une valeur initiale en calculant des sommes partielles successives, ou calcule le résultat des résultats partiels successifs obtenus de la même façon en utilisant une opération binaire spécifiée autre que la somme.|  
|[adjacent_difference (STL/CLR)](../dotnet/adjacent-difference-stl-clr.md)|Détermine les différences successives entre chaque élément et son prédécesseur au sein d'une plage d'entrée, puis génère les résultats dans une plage de destination ou calcule le résultat d'une procédure généralisée dans laquelle l'opération de différence est remplacée par une autre opération binaire spécifiée.|  
|[inner_product (STL/CLR)](../dotnet/inner-product-stl-clr.md)|Calcule la somme du produit d’éléments de deux plages et l’ajoute à une valeur initiale spécifiée, ou calcule le résultat d’une procédure généralisée dans laquelle les opérations binaires de somme et de produit sont remplacées par d’autres opérations binaires spécifiées.|  
|[partial_sum (STL/CLR)](../dotnet/partial-sum-stl-clr.md)|Calcule une série de sommes dans une plage d’entrée du premier élément via le `i`élément th et stocke le résultat de chaque somme dans `i`ième élément d’une plage de destination ou calcule le résultat d’une procédure généralisée où l’opération de somme est remplacé par une autre opération binaire spécifiée.|  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<cliext/numeric >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [Référence de bibliothèque STL/CLR](../dotnet/stl-clr-library-reference.md)