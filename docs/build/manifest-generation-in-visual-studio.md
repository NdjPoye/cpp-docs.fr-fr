---
title: "G&#233;n&#233;ration de manifeste dans Visual Studio | Microsoft Docs"
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
  - "manifestes (C++)"
ms.assetid: 0af60aa9-d223-42cd-8426-b3fc543a2a81
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# G&#233;n&#233;ration de manifeste dans Visual Studio
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La génération d'un fichier manifeste pour un projet particulier peut se contrôler dans la boîte de dialogue **Pages de propriétés** du projet.  Dans l'onglet **Propriétés de configuration**, cliquez sur **Éditeur de liens**, puis sur **Fichier manifeste** et enfin sur**Génération d'un manifeste**.  Par défaut, les propriétés de projet des nouveaux projets sont configurées pour générer un fichier manifeste.  Il est néanmoins possible de désactiver la génération du manifeste dans un projet à l'aide de la propriété **Génération d'un manifeste** du projet.  Lorsque cette propriété a la valeur **Oui**, le manifeste de ce projet est généré.  Sinon, l'éditeur de liens ignore les informations d'assembly lors de la résolution des dépendances du code d'application, et ne génère pas le manifeste.  
  
 Le système de génération de Visual Studio permet d'incorporer le manifeste dans le dernier fichier d'application binaire ou de le générer comme un fichier externe.  Ce comportement est contrôlé par l'option **Incorporer le manifeste** dans la boîte de dialogue **Propriétés du projet**.  Pour définir cette propriété, ouvrez le nœud **Outil manifeste**, puis sélectionnez  **Entrée et sortie**.  Si le manifeste n'est pas incorporé, il est généré comme un fichier externe et enregistré dans le même répertoire que le dernier fichier binaire.  Si le manifeste est incorporé, Visual Studio incorpore les derniers manifestes à l'aide de la procédure suivante :  
  
1.  Après avoir compilé le code source en fichiers objets, l'éditeur de liens rassemble des informations d'assembly dépendantes.  En liant le dernier fichier binaire, il génère un manifeste intermédiaire, qui sera utilisé ultérieurement pour générer le dernier manifeste.  
  
2.  Une fois le manifeste intermédiaire et la liaison terminés, l'outil manifeste sera exécuté pour fusionner un manifeste final et l'enregistrer en tant que fichier externe.  
  
3.  Le système de génération du projet détecte ensuite si le manifeste généré par l'outil manifeste contient des informations différentes de celles du manifeste déjà incorporé dans le fichier binaire.  
  
4.  Si le manifeste incorporé dans le fichier binaire est différent de celui qui est généré par l'outil manifeste ou si le fichier binaire ne contient pas de manifeste incorporé, Visual Studio appellera l'éditeur de liens une nouvelle fois pour incorporer le fichier manifeste externe dans le fichier binaire en tant que ressource.  
  
5.  Si le manifeste incorporé dans le fichier binaire est le même que celui qui est généré par l'outil manifeste, la génération passera aux étapes de build suivantes.  
  
 Le manifeste est incorporé à l'intérieur du fichier binaire final en tant que ressource texte et peut être visualisé en ouvrant le dernier fichier binaire comme un fichier dans Visual Studio.  Pour garantir que le manifeste renvoie aux bonnes bibliothèques, suivez les étapes décrites dans [Fonctionnement des dépendances d'une application Visual C\+\+](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md) ou les suggestions décrites dans la section [Dépannage](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md).  
  
## Voir aussi  
 [Comment : incorporer un manifeste à une application C\/C\+\+](../build/how-to-embed-a-manifest-inside-a-c-cpp-application.md)   
 [Assemblys privés](_win32_private_assemblies)   
 [Outil Manifeste](http://msdn.microsoft.com/library/aa375649)   
 [Fonctionnement de la génération de manifestes pour les programmes C\/C\+\+](../build/understanding-manifest-generation-for-c-cpp-programs.md)