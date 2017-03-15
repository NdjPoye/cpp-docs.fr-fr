---
title: "Comment&#160;: activer IntelliSense pour des projets Makefile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCNMakeTool.IntelliSense"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IntelliSense, projets Makefile"
  - "projets Makefile, IntelliSense"
ms.assetid: 9443f453-f18f-4f12-a9a1-ef9dbf8b188f
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# Comment&#160;: activer IntelliSense pour des projets Makefile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

IntelliSense ne fonctionne pas dans l'IDE de projets Makefile Visual C\+\+ lorsque certains paramètres de projet, ou options du compilateur, sont incorrectement configurés.  Utilisez cette procédure pour configurer les projets Makefile Visual C\+\+, afin qu'IntelliSense fonctionne lorsque ces projets sont ouverts dans l'environnement de développement Visual Studio.  
  
### Pour permettre à IntelliSense de fonctionner avec les projets Makefile dans l'IDE  
  
1.  Ouvrez la boîte de dialogue **Pages de propriétés**.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../misc/how-to-open-project-property-pages.md).  
  
2.  Développez le nœud **Propriétés de configuration**.  
  
3.  Sélectionnez la page de propriétés de **NMAKE**, puis modifiez les propriétés figurant sous **IntelliSense** à votre convenance.  
  
    -   Définissez la propriété **Définitions de préprocesseur** pour définir n'importe quel symbole de préprocesseur dans votre projet Makefile.  Pour plus d'informations, consultez [\/D \(Définitions de préprocesseur\)](../build/reference/d-preprocessor-definitions.md).  
  
    -   Définissez la propriété **Chemin de recherche Include** de façon à spécifier la liste des répertoires dans lesquels le compilateur effectuera sa recherche afin de résoudre les références de fichier passées aux directives de préprocesseur dans votre projet Makefile.  Pour plus d'informations, consultez [\/I \(Autres répertoires Include\)](../build/reference/i-additional-include-directories.md).  
  
         Pour les projets qui sont générés à l'aide de CL.EXE depuis une fenêtre Commande, définissez la variable d'environnement **INCLUDE** de sorte de spécifier les répertoires dans lesquels le compilateur effectuera ses recherches pour résoudre les références de fichier qui sont passées aux directives de préprocesseur dans votre projet Makefile.  
  
    -   Définissez la propriété **Fichiers Include forcés** pour spécifier quels fichiers d'en\-tête traiter lors de la génération de votre projet Makefile.  Pour plus d'informations, consultez [\/FI \(Nom du fichier Include imposé\)](../build/reference/fi-name-forced-include-file.md).  
  
    -   Définissez la propriété **Chemin de recherche des assemblys** pour spécifier la liste des répertoires dans lesquels le compilateur effectuera ses recherches pour résoudre les références aux assemblys .NET dans votre projet.  Pour plus d'informations, consultez [\/AI \(Spécifier les répertoires des métadonnées\)](../build/reference/ai-specify-metadata-directories.md).  
  
    -   Définissez la propriété **Utilisation forcée des assemblys** pour spécifier quels assemblys .NET traiter lors de la génération de votre projet Makefile.  Pour plus d'informations, consultez [\/FU \(Nom du fichier \#using imposé\)](../build/reference/fu-name-forced-hash-using-file.md).  
  
    -   Définissez la propriété **Options supplémentaires** de façon à spécifier des commutateurs de compilation supplémentaires à utiliser par Intellisense lors de l'analyse des fichiers C\+\+.  
  
4.  Cliquez sur **OK** pour fermer les pages de propriétés.  
  
5.  Utilisez la commande **Enregistrer tout** pour enregistrer les paramètres modifiés du projet.  
  
 À la prochaine ouverture de votre projet Makefile dans l'environnement de développement Visual Studio, exécutez la commande **Nettoyer la solution**, puis la commande **Générer la solution** sur votre projet Makefile.  IntelliSense doit fonctionner correctement dans l'IDE.  
  
## Voir aussi  
 [Utilisation de la fonctionnalité IntelliSense](../Topic/Using%20IntelliSense.md)   
 [Référence NMAKE](../build/nmake-reference.md)   
 [Comment : créer un projet C\+\+ à partir d'un code existant](../ide/how-to-create-a-cpp-project-from-existing-code.md)