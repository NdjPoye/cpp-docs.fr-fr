---
title: Cibles | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: targets, specifying in NMAKE
ms.assetid: 826ee849-4278-4c6e-97c3-79a2b5fe6463
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a07947dc7de4529d8cef3aa0f104d529d0b95ea5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="targets"></a>Cibles
Dans une ligne de dépendance, spécifiez une ou plusieurs cibles, à l’aide de n’importe quel nom de fichier valide, le nom de répertoire, ou [pseudocible](../build/pseudotargets.md). Séparez plusieurs cibles par un ou plusieurs des espaces ou des tabulations. Les cibles ne respectent pas la casse. Chemins d’accès sont autorisées avec les noms de fichiers. Une cible ne peut pas dépasser 256 caractères. Si la cible qui précède le signe deux-points est un caractère unique, utilisez un espace de séparation ; Sinon, NMAKE interprète la combinaison lettre-signe deux-points comme un spécificateur de lecteur.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Sur quels éléments souhaitez-vous obtenir des informations supplémentaires ?  
 [Pseudocibles](../build/pseudotargets.md)  
  
 [Plusieurs cibles](../build/multiple-targets.md)  
  
 [Dépendances cumulatives](../build/cumulative-dependencies.md)  
  
 [Cibles dans des blocs de description multiples](../build/targets-in-multiple-description-blocks.md)  
  
 [Effets secondaires des dépendances](../build/dependency-side-effects.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Blocs de description](../build/description-blocks.md)