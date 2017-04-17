---
title: "Comment&#160;: cr&#233;er des applications console CLR (C++/CLI) | Microsoft Docs"
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
  - "applications console, modèles"
  - "applications console CLR, modèle de projet"
ms.assetid: e89bce3c-706f-4ae0-8a90-cb1a0f674e70
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: cr&#233;er des applications console CLR (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser le modèle Application console pour créer un projet d’application console qui a déjà les références et les fichiers principaux d’un projet.  
  
 En général, une application console est compilée en un fichier exécutable autonome, mais elle n’a pas d’interface utilisateur graphique. Un utilisateur exécute l’application console à l’invite de commandes et utilise l’invite de commandes pour émettre des instructions destinées à l’application en cours d’exécution. L’application fournit également des informations de sortie, toujours à l’invite de commandes. L’interactivité directe d’une application console constitue un bon moyen d’apprendre les techniques de programmation sans se soucier de l’implémentation d’une interface utilisateur.  
  
 Quand vous utilisez le modèle Application console pour créer un projet, il ajoute automatiquement ces références et ces fichiers :  
  
-   Références à ces espaces de noms .NET Framework :  
  
    -   [System](https://msdn.microsoft.com/en-us/library/system.appdomainmanager.appdomainmanager.aspx) : contient des classes fondamentales et des classes de base qui définissent des valeurs et des types de données de référence, des événements et des gestionnaires d’événements, des interfaces, des attributs et des exceptions de traitement couramment utilisés.  
  
    -   mscorlib  : DLL de l’assembly qui prend en charge le développement .NET Framework.  
  
-   Fichiers sources :  
  
    -   Console \(fichier .cpp\) : le fichier source et le point d’entrée principal entrée dans l’application que vous venez de créer. Il identifie le fichier .dll du projet et l’espace de noms du projet. Fournissez votre propre code dans ce fichier.  
  
    -   AssemblyInfo.cpp : contient des attributs, fichiers, ressources, types, informations de contrôle de version, informations de signature, etc., que vous pouvez utiliser pour modifier les métadonnées de l’assembly du projet. Pour plus d’informations, consultez [Contenu d'un assembly](../Topic/Assembly%20Contents.md).  
  
    -   Stdafx.cpp : utilisé pour générer un fichier d’en\-tête précompilé nommé Win32.pch et un fichier de types précompilé nommé StdAfx.obj.  
  
-   Fichiers d’en\-tête :  
  
    -   Stdafx.h : utilisé pour générer un fichier d’en\-tête précompilé nommé Win32.pch et un fichier de types précompilé nommé StdAfx.obj.  
  
    -   resource.h : un fichier include généré pour app.rc.  
  
-   Fichiers de ressources :  
  
    -   app.rc : le fichier de script de ressources d’un programme.  
  
    -   app.ico : le fichier icône d’un programme.  
  
-   ReadMe.txt : décrit les fichiers du projet.  
  
## Pour créer un projet d’application console CLR \(Common Language Runtime\)  
  
1.  Dans la barre de menus, sélectionnez **Fichier**, **Nouveau**, **Projet**.  
  
2.  Dans la boîte de dialogue **Nouveau projet**, sous **Modèles installés**, sélectionnez le nœud **Visual C\+\+**, sélectionnez le nœud **CLR**, puis sélectionnez le modèle Application console.  
  
3.  Dans la zone **Nom**, entrez un nom unique pour votre application.  
  
     Vous pouvez spécifier d’autres paramètres pour le projet et la solution, mais ils ne sont pas obligatoires.  
  
4.  Sélectionnez le bouton **OK**.  
  
## Voir aussi  
 [NOTINBUILD Procédure : création d’applications console CLR](http://msdn.microsoft.com/fr-fr/b8af4197-e65f-4b17-b18e-b9e92965d026)   
 [Projets CLR](../ide/files-created-for-clr-projects.md)   
 [NIB : Gestion des éléments dans les projets](http://msdn.microsoft.com/fr-fr/762e606b-7f44-4b66-97a1-e30a703654a0)