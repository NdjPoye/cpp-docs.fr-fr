---
title: "Fichier Templates.inf | Microsoft Docs"
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
  - "Assistants personnalisés, fichiers modèles"
ms.assetid: 93d60d27-2402-4dc8-a829-e97417ccea49
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fichier Templates.inf
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Templates.inf est un fichier texte qui contient une liste de modèles à restituer pour le projet.  
  
 Templates.inf étant lui\-même un [fichier modèle](../ide/template-files.md), vous pouvez utiliser des directives pour indiquer quels fichiers doivent être inclus dans un projet, en fonction des sélections de l'utilisateur.  Consultez [Directives de modèle](../ide/template-directives.md) pour obtenir la liste des directives utilisables dans ce fichier.  
  
## Exemple  
  
```  
Template1.txt  
Template2.txt  
  [!if TYPE_A]  
TemplateOptionA.h  
TemplateOptionA.cpp  
  [!else]  
TemplateOptionB.h  
TemplateOptionB.cpp  
  [!endif]  
```  
  
 **CreateCustomInfFile** restitue Templates.inf sous forme d'un fichier texte temporaire, qui doit ensuite être supprimé après traitement des fichiers.  
  
## Exemple  
  
```  
var InfFile = CreateCustomInfFile();  
AddFilesToProject(selProj, strProjectName, InfFile);  
InfFile.Delete();  
```  
  
 Consultez [Le fichier Jscript](../ide/jscript-file.md) pour plus d'informations.  
  
## Voir aussi  
 [Fichiers créés pour votre Assistant](../ide/files-created-for-your-wizard.md)   
 [Assistant personnalisé](../ide/custom-wizard.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)