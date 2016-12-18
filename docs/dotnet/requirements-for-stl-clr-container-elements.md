---
title: "Sp&#233;cifications pour les &#233;l&#233;ments de conteneur STL/CLR | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "conteneurs, STL"
  - "conteneurs, STL/CLR"
  - "bibliothèque C++ standard, conteneurs de classes de modèle"
  - "STL/CLR, conteneurs"
ms.assetid: 59ab240c-15bf-4701-a9f9-e7c56e5ab53f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Sp&#233;cifications pour les &#233;l&#233;ments de conteneur STL/CLR
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Tous les types référence qui sont insérés dans des conteneurs STL\/CLR doit être, au minimum, les éléments suivants :  
  
-   Constructeur de copie public.  
  
-   Un opérateur d'assignation public.  
  
-   Un destructeur public.  
  
 En outre, les conteneurs associatifs comme [set](../dotnet/set-stl-clr.md) et [carte](../dotnet/map-stl-clr.md) doivent disposer d'un opérateur de comparaison public défini, qui est `operator<` par défaut.  Certaines opérations sur les conteneurs peuvent également nécessiter de définir un constructeur public par défaut et un opérateur d'équivalence public.  
  
 Comme les types référence, les types de valeurs et les handles vers des types référence qui doivent être insérés dans un conteneur associatif doivent disposer d'un opérateur de comparaison par exemple `operator<` définies.  Les spécifications liées à un constructeur de copie public, un opérateur d'assignation public, et un destructeur public n'existent pas pour les types de valeurs ou des handles vers des types référence.  
  
## Voir aussi  
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)