---
title: "/MAP (G&#233;n&#233;rer fichier de mappage) | Microsoft Docs"
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
  - "/map"
  - "VC.Project.VCLinkerTool.MapFileName"
  - "VC.Project.VCLinkerTool.GenerateMapFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MAP (option de l'éditeur de liens)"
  - "générer fichier de mappage (option de l'éditeur de liens)"
  - "MAP (option de l'éditeur de liens)"
  - "-MAP (option de l'éditeur de liens)"
  - "fichier de mappage (option de l'éditeur de liens)"
  - "fichiers de mappage, créer avec l'éditeur de liens"
  - "fichiers de mappage, informations sur le programme lié"
  - "fichiers de mappage, spécifier un nom de fichier"
ms.assetid: 9ccce53d-4e36-43da-87b0-7603ddfdea63
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /MAP (G&#233;n&#233;rer fichier de mappage)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MAP[:filename]  
```  
  
## Notes  
 où :  
  
 *filename*  
 désigne un nom spécifié par l'utilisateur pour le fichier de mappage.  Il remplace le nom par défaut.  
  
## Notes  
 L'option \/MAP indique à l'Éditeur de liens de créer un fichier de mappage.  
  
 Par défaut, l'éditeur de liens nomme le fichier de mappage avec le nom de base du programme et l'extension .map.  L'argument facultatif *filename* vous permet de substituer le nom par défaut d'un fichier de mappage.  
  
 Un fichier de mappage contient les informations suivantes sur le programme en cours de liaison :  
  
-   Le nom du module, qui est le nom de base du fichier ;  
  
-   la date provenant de l'en\-tête du fichier de programme \(et non du système de fichiers\) ;  
  
-   une liste de groupes du programme, avec l'adresse de départ \(*section*:*offset*\) de chaque groupe, sa longueur, son nom et sa classe ;  
  
-   une liste de symboles publics avec chaque adresse \(*section*:*offset*\), le nom du symbole, l'adresse complète et le fichier .obj dans lequel le symbole est défini.  
  
-   le point d'entrée \(*section*:*offset*\).  
  
 L'option [\/MAPINFO](../../build/reference/mapinfo-include-information-in-mapfile.md) spécifie les informations supplémentaires à inclure dans le fichier de mappage.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Déboguer**.  
  
4.  Modifiez la propriété **Génération d'un fichier de mappage**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateMapFile%2A> et <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MapFileName%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)