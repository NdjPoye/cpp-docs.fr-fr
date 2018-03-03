---
title: "LNK4105 d’avertissement des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4105
dev_langs:
- C++
helpviewer_keywords:
- LNK4105
ms.assetid: 6c7bebf4-4ea6-4533-a6ed-e563d43abbd7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 913a6da056908def8df5aab1c2425ef9a187c1e2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4105"></a>Avertissement des outils Éditeur de liens LNK4105
aucun argument spécifié avec l’option 'option' ; option ignorée  
  
 Cet avertissement se produit uniquement lorsque le [/LIBPATH](../../build/reference/libpath-additional-libpath.md) option est définie. Si aucun répertoire n’est spécifiée avec cette option, l’éditeur de liens ignore l’option et génère ce message d’avertissement.  
  
 Si vous n’avez pas besoin remplacer les paramètres de bibliothèque d’environnement existant, supprimez l’option /LIBPATH à partir de la ligne de commande de l’éditeur de liens. Si vous souhaitez utiliser un autre chemin de recherche pour les bibliothèques, spécifiez le chemin d’accès à l’autre après l’option /LIBPATH.  
  
## <a name="example"></a>Exemple  
  
```  
link /libpath:c:\filepath\lib bar.obj  
```  
  
 l’éditeur de liens pour rechercher les bibliothèques requises dans `c:\filepath\lib` avant de les rechercher dans les emplacements par défaut.