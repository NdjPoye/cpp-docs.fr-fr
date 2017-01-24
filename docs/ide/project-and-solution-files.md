---
title: "Fichiers projet et solution | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.files.projectandsolution"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".sdf, fichier de base de données de navigation"
  - "fichier de base de données de navigation, .sdf"
  - "types de fichiers (C++), makefiles"
  - "types de fichiers (C++), fichiers projet"
  - "projets Makefile"
  - "fichiers projet (C++)"
ms.assetid: 5823b954-36cf-42d3-8fd5-25bab3ef63d9
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fichiers projet et solution
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les fichiers suivants sont créés en même temps que vous créez un projet dans Visual Studio.  Ils servent à gérer les fichiers projet de la solution.  
  
|Nom de fichier|Emplacement du répertoire|Emplacement dans l'Explorateur de solutions|Description|  
|--------------------|-------------------------------|-------------------------------------------------|-----------------|  
|*NomSol*.sln|*NomProj*|Non affiché dans l'Explorateur de solutions|Fichier *solution*.  Permet d'organiser tous les éléments d'un ou plusieurs projets dans une même solution.|  
|*NomProj*.suo|*NomProj*|Non affiché dans l'Explorateur de solutions|Fichier d'*options de solution*.  Permet de stocker les personnalisations de la solution pour que chaque fois que vous ouvrez un projet ou un fichier de la solution, il ait l'apparence et le comportement que vous attendez.|  
|*NomProj*.vcxproj|*NomProj*|Non affiché dans l'Explorateur de solutions|Fichier *projet*.  Permet de stocker les informations propres à chaque projet.  \(Dans les versions antérieures, ce fichier était nommé *NomProj*.vcproj ou *NomProj*.dsp.\) Pour obtenir un exemple de fichier projet Visual C\+\+, consultez [Fichiers projet](../ide/project-files.md).|  
|*NomProj*.sdf|*NomProj*|Non affiché dans l'Explorateur de solutions|Fichier de *base de données de navigation*.  Prend en charge les fonctionnalités de navigation telles que **Atteindre la définition**, **Rechercher toutes les références** et **Affichage de classes**.  Il est généré en analysant les fichiers d'en\-tête.|  
|*NomProj.*vcxproj.filters|*NomProj*|Non affiché dans l'Explorateur de solutions|Fichier de *filtres*.  Permet de spécifier l'emplacement d'un fichier ajouté à la solution.  Par exemple, un fichier .h sera placé dans le nœud **Fichiers d'en\-tête**.|  
|*NomProj.*vcxproj.User|*NomProj*|Non affiché dans l'Explorateur de solutions|Fichier *utilisateur de migration*.  Suite à la migration d'un projet à partir de Visual Studio 2008, ce fichier contient des informations qui ont été converties à partir d'un fichier .vsprops.|  
|*NomProj*.idl|*NomProj*|Source|\(Propre au projet\) Contient le code source IDL \(Interface Description Langage\) d'une bibliothèque de types de contrôles.  Visual C\+\+ se sert de ce fichier pour générer une bibliothèque de types.  La bibliothèque générée expose l'interface du contrôle aux autres clients Automation.  Pour plus d'informations, consultez [Fichier IDL \(Interface Definition Language\)](http://msdn.microsoft.com/library/windows/desktop/aa378712) dans le [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)].|  
|Readme.txt|*NomProj*|Projet|Fichier *Lisez\-moi*.  Généré par l'Assistant Application, il décrit les fichiers contenus dans un projet.|  
  
## Voir aussi  
 [Types de fichiers créés pour les projets Visual C\+\+](../ide/file-types-created-for-visual-cpp-projects.md)