---
title: "R&#233;f&#233;rence de biblioth&#232;que STL/CLR | Microsoft Docs"
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
  - "cliext (répertoire)"
  - "STL/CLR (bibliothèque)"
  - "STL/CLR, redistribution"
ms.assetid: a9d9ca00-7bf2-48c1-b205-3ae6f8c25f82
caps.latest.revision: 17
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# R&#233;f&#233;rence de biblioth&#232;que STL/CLR
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La bibliothèque STL\/CLR est un package de la bibliothèque de modèles standard \(STL\), un sous\-ensemble de la bibliothèque C\+\+ standard, qui peut être utilisé avec C\+\+ et le Common Language Runtime \(CLR\) du .NET Framework.  Grâce à STL\/CLR, vous pouvez utiliser tous les conteneurs, itérateurs et algorithmes de STL dans un environnement managé.  
  
 Pour utiliser STL\/CLR :  
  
-   Incluez les en\-têtes du sous\-répertoire include **cliext** au lieu des équivalents habituels de la bibliothèque C\+\+ standard.  
  
-   Qualifiez les noms de bibliothèques avec `cliext::` au lieu de `std::`.  
  
 STL\/CLR expose les types et interfaces génériques qu'il utilise dans les scénarios d'assembly croisé de l'assembly .NET. **Microsoft.VisualC.STLCLR.dll**.  Cette DLL est incluse dans .NET Framework 3.5.  Si vous redistribuez une application qui utilise STL\/CLR, vous devez inclure le .NET Framework 3.5, ainsi que toutes les autres bibliothèques Visual C\+\+ que votre projet utilise, dans la section des dépendances de votre projet d'installation.  
  
## Dans cette section  
 [cliext, espace de noms](../dotnet/cliext-namespace.md)  
 Présente l'espace de noms qui contient tous les types de la bibliothèque STL\/CLR.  
  
 [STL\/CLR, conteneurs](../dotnet/stl-clr-containers.md)  
 Fournit une vue d'ensemble des conteneurs présents dans la bibliothèque C\+\+ standard, notamment les spécifications relatives aux éléments de conteneur, les types d'éléments qui peuvent être insérés et les problèmes de propriété.  
  
 [Spécifications pour les éléments de conteneur STL\/CLR](../dotnet/requirements-for-stl-clr-container-elements.md)  
 Décrit la configuration minimale requise pour tous les types référence qui sont insérés dans des conteneurs STL.  
  
 [Comment : convertir une collection .NET en conteneur STL\/CLR](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)  
 Décrit comment convertir une collection .NET en un conteneur STL\/CLR.  
  
 [Comment : convertir un conteneur STL\/CLR en collection .NET](../dotnet/how-to-convert-from-a-stl-clr-container-to-a-dotnet-collection.md)  
 Décrit comment convertir un conteneur STL\/CLR en une collection .NET.  
  
 [Comment : exposer un conteneur STL\/CLR d'un assembly](../dotnet/how-to-expose-an-stl-clr-container-from-an-assembly.md)  
 Montre comment afficher les éléments de plusieurs conteneurs STL\/CLR écrits dans un assembly C\+\+.  
  
 En outre, cette section décrit également les composants suivants de STL\/CLR :  
  
|||  
|-|-|  
|[adapter](../dotnet/adapter-stl-clr.md)|[algorithm](../dotnet/algorithm-stl-clr.md)|  
|[deque](../dotnet/deque-stl-clr.md)|[for each, in](../dotnet/for-each-in.md)|  
|[functional](../dotnet/functional-stl-clr.md)|[hash\_map](../dotnet/hash-map-stl-clr.md)|  
|[hash\_multimap](../dotnet/hash-multimap-stl-clr.md)|[hash\_multiset](../dotnet/hash-multiset-stl-clr.md)|  
|[hash\_set](../dotnet/hash-set-stl-clr.md)|[list](../dotnet/list-stl-clr.md)|  
|[map](../dotnet/map-stl-clr.md)|[multimap](../dotnet/multimap-stl-clr.md)|  
|[multiset](../dotnet/multiset-stl-clr.md)|[numériques](../dotnet/numeric-stl-clr.md)|  
|[priority\_queue](../dotnet/priority-queue-stl-clr.md)|[queue](../dotnet/queue-stl-clr.md)|  
|[set](../dotnet/set-stl-clr.md)|[pile](../dotnet/stack-stl-clr.md)|  
|[utility](../dotnet/utility-stl-clr.md)|[vecteur](../dotnet/vector-stl-clr.md)|  
  
## Voir aussi  
 [Bibliothèque standard C\+\+](../standard-library/cpp-standard-library-reference.md)