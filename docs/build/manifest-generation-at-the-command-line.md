---
title: "G&#233;n&#233;ration de manifeste au niveau de la ligne de commande | Microsoft Docs"
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
  - "outil Manifeste (mt.exe)"
  - "manifestes (C++)"
ms.assetid: fc2ff255-82b1-4c44-af76-8405c5850292
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# G&#233;n&#233;ration de manifeste au niveau de la ligne de commande
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque l'on génère des applications C\/C\+\+ à partir de la ligne de commande à l'aide de nmake ou d'outils semblables, le manifeste n'est généré qu'une fois que l'éditeur de liens a traité tous les fichiers objets et construit le fichier binaire final.  L'éditeur de liens rassemble les informations d'assembly stockées dans les fichiers objets et les combine au sein d'un fichier manifeste final.  Par défaut, l'éditeur de liens génère un fichier nommé \<binary\_name\>.\<extension\>.manifest pour décrire le fichier binaire final.  L'éditeur de liens n'incorpore pas de fichier manifeste au fichier binaire et ne peut générer de manifeste que sous la forme d'un fichier externe.  Plusieurs méthodes permettent d'incorporer un manifeste dans le fichier binaire final, par exemple en utilisant l'[outil Manifeste \(mt.exe\)](http://msdn.microsoft.com/library/aa375649) ou en compilant le manifeste en un fichier de ressources.  Il est important de se rappeler que des règles spécifiques doivent être observées au moment de l'incorporation d'un manifeste dans le fichier binaire final afin d'activer des fonctions comme la liaison incrémentielle, la signature ou les fonctions Modifier & Continuer.  Ces options, parmi d'autres, sont traitées dans [Comment : incorporer un manifeste à une application C\/C\+\+](../build/how-to-embed-a-manifest-inside-a-c-cpp-application.md) lorsqu'il s'agit de génération sur la ligne de commande.  
  
## Voir aussi  
 [Manifestes](http://msdn.microsoft.com/library/aa375365)   
 [\/INCREMENTAL \(Lier par incrément\)](../build/reference/incremental-link-incrementally.md)   
 [Assemblys de nom fort \(signature d'assembly\)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)   
 [Modifier&Continuer](../Topic/Edit%20and%20Continue.md)   
 [Fonctionnement de la génération de manifestes pour les programmes C\/C\+\+](../build/understanding-manifest-generation-for-c-cpp-programs.md)