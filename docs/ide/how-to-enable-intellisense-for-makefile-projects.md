---
title: "Comment : activer IntelliSense pour les projets Makefile | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.VCNMakeTool.IntelliSense
dev_langs: C++
helpviewer_keywords:
- Makefile projects, IntelliSense
- IntelliSense, Makefile projects
ms.assetid: 9443f453-f18f-4f12-a9a1-ef9dbf8b188f
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fae3ec35259250f71ad672d9468b991033608ae4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-enable-intellisense-for-makefile-projects"></a>Comment : activer IntelliSense pour des projets Makefile
IntelliSense ne fonctionne pas dans l’IDE pour les projets makefile Visual C++ lorsque certains paramètres ou les options du compilateur, de projets sont configurés correctement. Utilisez cette procédure pour configurer les projets makefile Visual C++, afin qu’IntelliSense fonctionne lorsque ces projets sont ouverts dans l’environnement de développement Visual Studio.  
  
### <a name="to-enable-intellisense-for-makefile-projects-in-the-ide"></a>Pour activer IntelliSense pour les projets makefile dans l’IDE  
  
1.  Ouvrez le **Pages de propriétés** boîte de dialogue. Pour plus d’informations, consultez [utilisation des propriétés de projet](../ide/working-with-project-properties.md).  
  
2.  Développez le **propriétés de Configuration** nœud.  
  
3.  Sélectionnez le **NMake** propriété page, puis modifiez les propriétés sous **IntelliSense** selon le cas.  
  
    -   Définir le **définitions de préprocesseur** propriété pour définir les symboles de préprocesseur dans votre projet makefile. Consultez [/D (définitions de préprocesseur)](../build/reference/d-preprocessor-definitions.md), pour plus d’informations.  
  
    -   Définir le **chemin de recherche Include** propriété pour spécifier la liste des répertoires dans lesquels le compilateur recherche pour résoudre les références de fichier qui sont passées aux directives de préprocesseur dans votre projet makefile. Consultez [/I (autres répertoires Include)](../build/reference/i-additional-include-directories.md), pour plus d’informations.  
  
         Pour les projets qui sont générés à l’aide de CL. L’exécutable à partir d’une fenêtre de commande, définissez la **INCLUDE** variable d’environnement pour spécifier les répertoires dans lesquels le compilateur recherche pour résoudre les références de fichier qui sont passées aux directives de préprocesseur dans votre projet makefile.  
  
    -   Définir le **forcés** propriété pour spécifier quels fichiers d’en-tête au processus lors de la génération de votre projet makefile. Consultez [/FI (nom forcé inclure de fichier)](../build/reference/fi-name-forced-include-file.md), pour plus d’informations.  
  
    -   Définir le **chemin de recherche** propriété pour spécifier la liste des répertoires dans lesquels le compilateur recherche pour résoudre les références aux assemblys .NET dans votre projet. Consultez [/AI (spécifier les répertoires des métadonnées)](../build/reference/ai-specify-metadata-directories.md), pour plus d’informations.  
  
    -   Définir le **Utilisation forcée des assemblys** propriété pour spécifier quels assemblys .NET traiter lors de la génération de votre projet makefile. Consultez [/FU (nom forcé #using fichier)](../build/reference/fu-name-forced-hash-using-file.md), pour plus d’informations.  
  
    -   Définir le **des Options supplémentaires** propriété pour spécifier des commutateurs de compilation supplémentaires à utiliser par Intellisense lors de l’analyse des fichiers C++.  
  
4.  Cliquez sur **OK** pour fermer les pages de propriétés.  
  
5.  Utilisez le **Enregistrer tout** commande pour enregistrer les paramètres modifiés du projet.  
  
 La prochaine fois que vous ouvrez votre projet makefile dans l’environnement de développement Visual Studio, exécutez le **nettoyer la Solution** commande, puis le **générer la Solution** commande sur votre projet makefile. IntelliSense doit fonctionner correctement dans l’IDE.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de la fonctionnalité IntelliSense](/visualstudio/ide/using-intellisense)   
 [Référence NMAKE](../build/nmake-reference.md)   
 [Guide pratique pour créer un projet C++ à partir d’un code existant](../ide/how-to-create-a-cpp-project-from-existing-code.md)