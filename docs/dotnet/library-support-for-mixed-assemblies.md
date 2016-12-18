---
title: "Prise en charge de biblioth&#232;que pour les assemblys mixtes | Microsoft Docs"
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
  - "bibliothèques (C++), assemblys mixtes"
  - "assemblys mixtes (C++), prise en charge de la bibliothèque"
  - "msvcm90[d].dll"
  - "msvcmrt[d].lib"
ms.assetid: 1229595c-9e9d-414d-b018-b4e4c727576d
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Prise en charge de biblioth&#232;que pour les assemblys mixtes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ prend en charge l'utilisation de la bibliothèque C\+\+ standard, la bibliothèque CRT, ATL et MFC pour les applications compilées avec [\/clr \(Compilation pour le Common Language Runtime\)](../build/reference/clr-common-language-runtime-compilation.md).  Cela autorise les applications existantes qui utilisent ces bibliothèques à utiliser aussi des fonctionnalités .NET Framework.  
  
 Cette prise en charge introduit les nouvelles DLL et bibliothèques d'importation suivantes :  
  
-   Msvcmrt \[d\] .lib si vous compilez avec \/clr.  Liens d'assemblys mixtes vers cette bibliothèque d'importation.  
  
-   Msvcm90 \[d\] .dll et Msvcurt \[d\] .lib si vous compilez avec \/clr:pure.  La DLL est un assembly mixte qui fournit la prise en charge du runtime C managé \(CRT\), et fait partie d'un assembly managé installé dans le Global Assembly Cache \(GAC\).  Les assemblys purs se lient à cette bibliothèque d'importation et finissent liés à Msvcm90.dll.  
  
 Cette prise en charge offre plusieurs avantages connexes :  
  
-   Le CRT et la bibliothèque C\+\+ standard sont disponibles pour le code à la fois mixte et pur.  Le CRT et la bibliothèque C\+\+ standard fournis ne sont pas vérifiables ; finalement, vos appels sont encore routés aux mêmes CRT et bibliothèque C\+\+ standard que vous utilisez à partir du code natif.  
  
-   Gestion des exceptions unifiée correcte dans les images pures et mixtes.  
  
-   Initialisation statique de variables C\+\+ dans les images pures et mixtes.  
  
-   Prise en charge des variables par Appdomain et par processus dans le code managé.  
  
-   Résout les problèmes de verrouillage du chargeur qui se sont appliqués aux DLL mixtes dans Visual C\+\+ .NET et Visual C\+\+ .NET 2003.  
  
 De plus, cette prise en charge présente les limitations suivantes :  
  
-   Uniquement le modèle de la DLL du CRT est pris en charge \(pour le code compilé avec à la fois \/clr ou \/clr:pure\).  
  
-   Vous ne pouvez pas mélanger des objets purs et mixtes dans une seule image si ces objets utilisent des bibliothèques Visual C\+\+ \(parce que tous les objets doivent être purs dans une image pure\).  Si vous faites ceci, vous obtenez des erreurs au moment de l'édition de liens.  
  
 Vous devez remplacer votre CLR \(Common Language Runtime\) par la version actuelle, sinon il n'est pas garanti qu'il fonctionne avec les versions antérieures.  Le code généré avec ces modifications ne s'exécutera pas sur CLR version 1.x.  
  
## Voir aussi  
 [Assemblys mixtes \(natif et managé\)](../dotnet/mixed-native-and-managed-assemblies.md)