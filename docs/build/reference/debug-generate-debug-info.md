---
title: "/DEBUG (G&#233;n&#233;rer les informations de d&#233;bogage) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.GenerateDebugInformation"
  - "/debug"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fichiers .pdb, générer les informations de débogage"
  - "/DEBUG (option de l'éditeur de liens)"
  - "DEBUG (option de l'éditeur de liens)"
  - "-DEBUG (option de l'éditeur de liens)"
  - "déboguer (C++), fichiers d'information de débogage"
  - "déboguer (C++), option de l'éditeur de liens"
  - "Générer les informations de débogage (option de l'éditeur de liens)"
  - "fichiers PDB"
  - "fichiers pdb, générer les informations de débogage"
  - "bases de données de programme (C++)"
ms.assetid: 1af389ae-3f8b-4d76-a087-1cdf861e9103
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /DEBUG (G&#233;n&#233;rer les informations de d&#233;bogage)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DEBUG  
```  
  
## Notes  
 L'option \/DEBUG crée des informations de débogage pour le fichier .exe ou DLL.  
  
 L'éditeur de liens place les informations de débogage dans une base de données de programme \(PDB\).  Il met à jour cette base PDB lors des générations suivantes du programme.  
  
 Un fichier .exe ou une DLL créés à des fins de débogage contient le nom et le chemin d'accès de la base PDB correspondante.  Le débogueur lit le nom incorporé et utilise la base PDB lors du débogage du programme.  L'éditeur de liens utilise le nom de base du programme ainsi que l'extension .pdb pour nommer la base de données du programme et incorpore le chemin d'accès lors de sa création.  Pour substituer cette valeur par défaut, définissez l'option [\/PDB](../../build/reference/pdb-use-program-database.md) et spécifiez un autre nom de fichier.  
  
 L'option [Numéros de ligne uniquement](../../build/reference/z7-zi-zi-debug-information-format.md) \(\/Zd\) ou [Compatible C7](../../build/reference/z7-zi-zi-debug-information-format.md) \(\/Z7\) du compilateur force ce dernier à quitter les informations de débogage dans les fichiers .obj.  Vous pouvez également utiliser l'option du compilateur [Base de données du programme](../../build/reference/z7-zi-zi-debug-information-format.md) \(\/Zi\) pour stocker les informations de débogage du fichier .obj dans une base PDB.  L'éditeur de liens recherche d'abord la base PDB de l'objet dans le chemin d'accès absolu écrit dans le fichier .obj, puis dans le répertoire contenant le fichier .obj.  Vous ne pouvez pas spécifier à l'éditeur de liens le nom de fichier ou l'emplacement du PDB d'un objet.  
  
 [\/INCREMENTAL](../../build/reference/incremental-link-incrementally.md) est implicite lorsque \/DEBUG est spécifié.  
  
 \/DEBUG modifie les valeurs par défaut de l'option [\/OPT](../../build/reference/opt-optimizations.md) en remplaçant REF par NOREF et ICF par NOICF \(ainsi, vous devrez spécifier explicitement \/OPT:REF ou \/OPT:ICF\).  
  
 Pour plus d'informations sur les fichiers .PDB et .DBG, consultez l'article de la Base de connaissances Q121366, INFO: PDB and DBG Files \- What They Are and How They Work \(article en anglais\).  Vous trouverez les articles de la Base de connaissances dans la bibliothèque MSDN ou à l'adresse [http:\/\/search.support.microsoft.com](http://support.microsoft.com/).  
  
 Il est impossible de créer un fichier .exe ou .dll contenant des informations de débogage.  Les informations de débogage sont toujours placées dans un fichier .pdb.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Débogage** .  
  
4.  Modifiez la propriété **Génération des informations de débogage**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateDebugInformation%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)