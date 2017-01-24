---
title: "Quelles techniques d&#39;optimisation dois-je utiliser pour am&#233;liorer les performances de l&#39;application cliente lors du chargement&#160;? | Microsoft Docs"
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
  - "DLL (C++), optimiser"
  - "optimisation (C++), DLL"
  - "performances (C++), DLL"
ms.assetid: 2f8bbfb5-08b9-4a35-8302-25a1966881b1
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Quelles techniques d&#39;optimisation dois-je utiliser pour am&#233;liorer les performances de l&#39;application cliente lors du chargement&#160;?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si votre DLL est une DLL normale liée de manière statique aux MFC, le fait de la convertir en une DLL normale liée de manière dynamique aux MFC a pour conséquence de réduire la taille du fichier.  
  
 Si la DLL compte un grand nombre de fonctions exportées, utilisez un fichier .def pour exporter les fonctions \(au lieu d'utiliser **\_\_declspec\(dllexport\)**\) et appliquez l'[attribut NONAME](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md) du fichier .def à chaque fonction exportée.  L'attribut NONAME a pour effet de stocker uniquement la valeur ordinale, sans le nom de la fonction, dans la table d'exportations de la DLL, ce qui réduit la taille du fichier.  
  
 Les DLL liées de manière implicite à une application sont chargées en même temps que celle\-ci.  Pour améliorer les performances lors du chargement, essayez de diviser la DLL en différentes DLL.  Placez dans une DLL toutes les fonctions dont l'application appelante a besoin immédiatement après le chargement et prévoyez une liaison implicite de l'application appelante avec cette DLL.  Placez les autres fonctions dont l'application appelante n'a pas besoin dans l'immédiat dans une autre DLL et faites en sorte que l'application soit liée de manière explicite à cette DLL.  Pour plus d'informations, consultez [Méthode de liaison à utiliser](../build/determining-which-linking-method-to-use.md).  
  
## Voir aussi  
 [Forum Aux Questions à propos des DLL](../build/dll-frequently-asked-questions.md)