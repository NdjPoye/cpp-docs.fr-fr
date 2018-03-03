---
title: "Génération de manifeste dans Visual Studio | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- manifests [C++]
ms.assetid: 0af60aa9-d223-42cd-8426-b3fc543a2a81
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3d701d73103ee2c5ac72eb36d9919132f0578b1b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="manifest-generation-in-visual-studio"></a>Génération de manifeste dans Visual Studio
Génération d’un fichier manifeste pour un projet particulier peut être contrôlée dans le projet **Pages de propriétés** boîte de dialogue. Sur le **propriétés de Configuration** , cliquez sur **l’éditeur de liens**, puis **le fichier manifeste**, puis **génération d’un manifeste**. Par défaut, les propriétés du projet de nouveaux projets sont définies pour générer un fichier manifest. Toutefois, il est possible de désactiver la génération du manifeste pour un projet à l’aide de la **génération d’un manifeste** propriété du projet. Lorsque cette propriété a la valeur **Oui**, le manifeste de ce projet est généré. Sinon, l’éditeur de liens ignore les informations d’assembly lors de la résolution des dépendances du code d’application et ne génère pas le manifeste.  
  
 Le système de génération dans Visual Studio permet le manifeste incorporé dans le fichier d’application binaire finale, ou généré comme un fichier externe. Ce comportement est contrôlé par le **incorporer le manifeste** option dans le **propriétés du projet** boîte de dialogue. Pour définir cette propriété, ouvrez le **outil manifeste** nœud, puis sélectionnez **d’entrée et sortie**. Si le manifeste n’est pas incorporé, il est généré comme un fichier externe et enregistré dans le même répertoire que le fichier binaire final. Si le manifeste est incorporé, Visual Studio incorpore les derniers manifestes à l’aide de la procédure suivante :  
  
1.  Une fois le code source est compilé dans des fichiers de l’objet, l’éditeur de liens collecte des informations de l’assembly dépendant. Lors de la liaison du fichier binaire final, l’éditeur de liens génère un manifeste intermédiaire qui est utilisé ultérieurement pour générer le manifeste final.  
  
2.  Une fois le manifeste intermédiaire et la liaison sont terminées, l’outil manifeste sera exécuté pour fusionner un manifeste final et l’enregistrer dans un fichier externe.  
  
3.  Le projet de système de génération, puis détecte si le manifeste généré par l’outil manifeste contient des informations différentes de celles du manifeste déjà incorporé dans le fichier binaire.  
  
4.  Si le manifeste incorporé dans le fichier binaire est différent de celui généré par l’outil manifeste, ou le fichier binaire ne contient pas de manifeste incorporé, Visual Studio appelle l’éditeur de liens une nouvelle fois pour incorporer le fichier manifest externe dans le fichier binaire en tant qu’un ressource.  
  
5.  Si le manifeste incorporé dans le fichier binaire est le même que le manifeste généré par l’outil manifeste, la génération passera aux étapes de build suivants.  
  
 Le manifeste est incorporé dans le fichier binaire final en tant que texte ressource et elle peut être affichée en ouvrant le fichier binaire final en tant que fichier dans Visual Studio. Pour vous assurer que le manifeste renvoie aux bonnes bibliothèques, suivez les étapes décrites dans [comprendre les dépendances d’une Application Visual C++](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md) ou suivez les suggestions décrites dans le [dépannage](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md) section.  
  
## <a name="see-also"></a>Voir aussi  
 [Comment : incorporer un manifeste à l’intérieur d’une Application C/C++](../build/how-to-embed-a-manifest-inside-a-c-cpp-application.md)   
 [À propos des assemblys privés](http://msdn.microsoft.com/library/ff951638)   
 [Outil manifeste](http://msdn.microsoft.com/library/aa375649)   
 [Présentation de la génération de manifeste pour les programmes C/C++](../build/understanding-manifest-generation-for-c-cpp-programs.md)