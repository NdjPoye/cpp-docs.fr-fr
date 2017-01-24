---
title: "Fichiers cr&#233;&#233;s pour les projets CLR | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "applications .NET, C++"
  - "projets Visual C++, programmer CLR"
ms.assetid: 59ae9020-5f26-4ad0-bbdd-97c2e2023a20
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fichiers cr&#233;&#233;s pour les projets CLR
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque vous utilisez des modèles Visual C\+\+ pour créer vos projets, plusieurs fichiers sont créés, selon le modèle que vous utilisez.  Le tableau suivant répertorie tous les fichiers qui sont créés par des modèles de projet pour les projets .NET Framework.  
  
|Nom du fichier|Description du fichier|  
|--------------------|----------------------------|  
|AssemblyInfo.cpp|Fichier contenant des informations \(attributs, fichiers, ressources, types, informations de versioning, informations de signature, etc.\) pour modifier les métadonnées de l'assembly du projet.  Pour plus d'informations, consultez [Contenu d'un assembly](../Topic/Assembly%20Contents.md).|  
|*nomproj*.asmx|Fichier texte référençant les classes managées qui encapsulent la fonctionnalité du service Web XML.|  
|*nomproj*.cpp|Principal fichier source et point d'entrée dans l'application créée par Visual Studio à votre intention.  Identifie le fichier .dll du projet et son espace de noms.  Fournissez votre propre code dans ce fichier.|  
|*nomproj*.vsdisco|Fichier de déploiement XML contenant des liens vers les autres ressources qui décrivent le service Web XML.|  
|*nomproj*.h|Principal fichier include pour le projet, contenant l'ensemble des déclarations, symboles globaux et directives `#include` pour les autres fichiers d'en\-tête.|  
|*nomproj*.sln|Fichier solution utilisé à l'intérieur de l'environnement de développement pour regrouper tous les éléments de votre projet dans une solution unique.|  
|*nomproj*.suo|Fichier d'options de solution utilisé dans l'environnement de développement.|  
|*projname.vcxproj*|Fichier projet utilisé dans l'environnement de développement, où sont stockées les informations spécifiques à ce projet.|  
|ReadMe.txt|Fichier qui décrit chaque fichier de votre projet en utilisant les noms de fichiers réels créés par le modèle.|