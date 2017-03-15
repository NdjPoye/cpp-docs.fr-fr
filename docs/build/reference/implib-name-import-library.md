---
title: "/IMPLIB (Nommer la biblioth&#232;que d&#39;importation) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/implib"
  - "VC.Project.VCLinkerTool.ImportLIbrary"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/IMPLIB (option de l'éditeur de liens)"
  - "IMPLIB (option de l'éditeur de liens)"
  - "-IMPLIB (option de l'éditeur de liens)"
  - "bibliothèques d'importation, substituer le nom par défaut"
ms.assetid: fe8f71ab-7055-41b5-8ef8-2b97cfa4a432
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /IMPLIB (Nommer la biblioth&#232;que d&#39;importation)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/IMPLIB:filename  
```  
  
## Notes  
 où :  
  
 *filename*  
 désigne un nom spécifié par l'utilisateur pour la bibliothèque d'importation.  Il remplace le nom par défaut.  
  
## Notes  
 L'option \/IMPLIB substitue le nom par défaut de la bibliothèque d'importation créé par LINK lorsqu'il génère un programme contenant des exportations.  Le nom par défaut est composé du nom de base du fichier de sortie principal et de l'extension .lib.  Un programme contient des exportations si au moins l'un des éléments suivants est spécifié :  
  
-   le mot clé [\_\_declspec\(dllexport\)](../../cpp/dllexport-dllimport.md) dans le code source ;  
  
-   une instruction [EXPORTS](../../build/reference/exports.md) dans un fichier .def ;  
  
-   une spécification [\/EXPORT](../../build/reference/export-exports-a-function.md) dans une commande LINK.  
  
 LINK ignore \/IMPLIB lorsqu'une bibliothèque d'importation n'est pas en cours de création.  Si aucune exportation n'est spécifiée, LINK ne crée pas de bibliothèque d'importation.  Si un fichier d'exportation est utilisé dans la génération, LINK considère qu'une bibliothèque d'importation existe déjà et n'en crée pas.  Pour plus d'informations sur les bibliothèques d'importation et les fichiers d'exportation, consultez [Référence LIB](../../build/reference/lib-reference.md).  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Avancé**.  
  
4.  Modifiez la propriété **Bibliothèque d'importation**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ImportLibrary%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)