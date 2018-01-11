---
title: "Présentation des étapes de génération personnalisée et les événements de Build | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- builds [C++], events
- custom build steps [C++], customizing builds
- events [C++], build
- custom build steps [C++]
- build steps [C++]
- build events [C++], order of events and build steps
- build steps [C++], build events
- builds [C++], custom build steps
ms.assetid: beb2f017-3e9f-4b2c-9b57-2572fd2628e4
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9abb7ff0b9a39656999e7a53b476056f7a5b1558
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="understanding-custom-build-steps-and-build-events"></a>Présentation des étapes de génération personnalisée et des événements de build
À partir de dans l’environnement de développement Visual C++, il existe trois façons de personnaliser le processus de génération :  
  
 **Étapes de génération personnalisée**  
 Une étape de génération personnalisée est une règle de génération associée à un projet. Une étape de génération personnalisée peut spécifier une ligne de commande à exécuter, aucune entrée supplémentaire ou fichiers de sortie et un message à afficher. Pour plus d’informations, consultez [Comment : ajouter une étape de génération personnalisée à des projets MSBuild](../build/how-to-add-a-custom-build-step-to-msbuild-projects.md).  
  
 **Outils de génération personnalisée**  
 Un outil de génération personnalisée est une règle de génération associée à un ou plusieurs fichiers. Une étape de génération personnalisée peut passer des fichiers d’entrée à un outil de génération personnalisée, ce qui engendre un ou plusieurs fichiers de sortie. Par exemple, les fichiers d’aide dans une application MFC sont générés avec un outil de génération personnalisée. Pour plus d’informations, consultez [Comment : ajouter des outils génération personnalisée à des projets MSBuild](../build/how-to-add-custom-build-tools-to-msbuild-projects.md) et [spécifiant des outils de génération personnalisée](../ide/specifying-custom-build-tools.md).  
  
 **Événements de build**  
 Événements de build permettent de personnaliser la génération d’un projet. Il existe trois événements de build : *pré-build*, *avant lien*, et *post-build*. Un événement de build vous permet de spécifier une action pour se produire à un moment précis dans le processus de génération. Par exemple, vous pouvez utiliser un événement de build pour enregistrer un fichier avec **regsvr32.exe** une fois le projet a fini la génération. Pour plus d’informations, consultez [spécifiant les événements de Build](../ide/specifying-build-events.md).  
  
 [Dépannage des personnalisations de Build](../ide/troubleshooting-build-customizations.md) peut vous aider à vérifier que vos étapes de génération personnalisée et générer des événements de s’exécutés comme prévu.  
  
 Étape de génération le format de sortie de personnalisé ou des événements de build peuvent également améliorer la facilité d’utilisation de l’outil. Pour plus d’informations, consultez [Mise en forme de la sortie d’une étape de génération personnalisée ou d’un événement de build](../ide/formatting-the-output-of-a-custom-build-step-or-build-event.md).  
  
 Étapes exécutées dans l’ordre suivant, ainsi que d’autres étapes de génération de la génération personnalisées et des événements de build :  
  
1.  Événement pré-Build  
  
2.  Outils sur des fichiers individuels de génération personnalisée  
  
3.  MIDL  
  
4.  Compilateur de ressources  
  
5.  Le compilateur C/C++  
  
6.  événement avant l'édition des liens  
  
7.  L’éditeur de liens ou le Générateur de bibliothèques (le cas échéant)  
  
8.  Outil Manifeste  
  
9. BSCMake  
  
10. Étape de génération personnalisée sur le projet  
  
11. Événement post-Build  
  
 Le `custom build step on the project` et un `post-build event` processus exécuter séquentiellement une fois que tous les autres généré.  
  
## <a name="see-also"></a>Voir aussi  
 [Génération de projets C++ dans Visual Studio](../ide/building-cpp-projects-in-visual-studio.md)   
 [Macros communs pour les propriétés et les commandes de génération](../ide/common-macros-for-build-commands-and-properties.md)   
 [Boîte de dialogue Outil Build ordre](http://msdn.microsoft.com/en-us/6204c5b1-7ce9-4948-9ff6-0268642ee14c)