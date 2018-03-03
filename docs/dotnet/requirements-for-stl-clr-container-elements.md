---
title: "Configuration requise pour les éléments de conteneur STL/CLR | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- C++ Standard Library, template class containers
- STL/CLR, containers
- containers, STL/CLR
- containers, C++ Standard Library
ms.assetid: 59ab240c-15bf-4701-a9f9-e7c56e5ab53f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3317e3c9349963fc24b37b421def05c475732fd8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="requirements-for-stlclr-container-elements"></a>Exigences pour les éléments de conteneur STL/CLR
Tous les types de référence sont insérées dans des conteneurs STL/CLR doivent avoir au minimum, les éléments suivants :  
  
-   Un constructeur de copie public.  
  
-   Un opérateur d’assignation de public.  
  
-   Un destructeur public.  
  
 En outre, les conteneurs associatifs comme [définir](../dotnet/set-stl-clr.md) et [carte](../dotnet/map-stl-clr.md) doivent avoir un opérateur de comparaison public défini, qui est `operator<` par défaut. Certaines opérations sur les conteneurs peuvent également nécessiter un constructeur public par défaut et un opérateur d’équivalence public à définir.  
  
 Comme les types référence, les types valeur et les descripteurs pour faire référence aux types qui doivent être insérés dans un conteneur associatif de doivent avoir un opérateur de comparaison tel que `operator<` défini. La configuration requise pour un constructeur de copie public, opérateur d’assignation public et un destructeur public n’existe pas pour les types valeur ou des handles vers des types référence.  
  
## <a name="see-also"></a>Voir aussi  
 [Référence de bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)