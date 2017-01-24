---
title: "Creating a New Custom or Data Resource | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.binary"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "custom resources [C++]"
  - "data resources [C++]"
  - "resources [Visual Studio], creating"
ms.assetid: 9918bf96-38fa-43a1-a384-572f95d84950
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating a New Custom or Data Resource
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez créer une ressource personnalisée ou une ressource de données en plaçant la ressource dans un fichier distinct à l’aide de la syntaxe de fichier de script de ressource normale, puis en incluant ce fichier en double\-cliquant sur votre projet dans l’Explorateur de solutions et en cliquant sur **Include des ressources** dans le menu contextuel.  
  
### Pour créer une ressource personnalisée ou une ressource de données  
  
1.  [Créez un fichier .rc](../windows/how-to-create-a-resource-script-file.md) qui contient la ressource personnalisée ou de données.  
  
     Vous pouvez taper des données personnalisées dans un fichier .rc en tant que chaînes entre guillemets terminées par un caractère Null, ou sous forme d’entiers au format octal, hexadécimal ou décimal.  
  
2.  Dans l’**Explorateur de solutions**, cliquez sur le fichier .rc de votre projet, puis sur **Include des ressources** dans le menu contextuel.  
  
3.  Dans la zone **Directives de compilation**, tapez une instruction **\#include** qui fournit le nom du fichier contenant la ressource personnalisée. Exemple :  
  
    ```  
    #include mydata.rc  
    ```  
  
     Assurez\-vous que la syntaxe et l’orthographe de ce que vous tapez sont correctes. Le contenu de la zone **Directives de compilation** est inséré dans le fichier de script de ressources exactement comme vous l’avez tapé.  
  
4.  Cliquez sur **OK** pour enregistrer les modifications.  
  
 Une autre façon de créer une ressource personnalisée consiste à importer un fichier externe en tant que ressource personnalisée. Pour plus d’informations, consultez [Importation et exportation de ressources](../windows/how-to-import-and-export-resources.md).  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l’ajout de fichiers de ressources aux projets managés, l’accès aux ressources, l’affichage de ressources statiques et l’assignation de chaînes de ressources à des propriétés, et ceci manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Spécifications  
  
 Win32  
  
## Voir aussi  
 [Binary Editor](../mfc/binary-editor.md)