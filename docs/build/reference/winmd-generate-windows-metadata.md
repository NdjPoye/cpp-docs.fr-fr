---
title: "/WINMD (g&#233;n&#233;rer des m&#233;tadonn&#233;es Windows) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.GenerateWindowsMetadata"
dev_langs: 
  - "C++"
ms.assetid: bcfb4901-411e-4c9e-9f78-23028b6e5fcc
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /WINMD (g&#233;n&#233;rer des m&#233;tadonn&#233;es Windows)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Active la génération d'un fichier de métadonnées Windows Runtime \(.winmd\) .  
  
```  
  
/WINMD[:{NO|ONLY}]  
```  
  
## Notes  
 \/WINMD  
 Le paramètre par défaut pour les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] .  L'éditeur de liens génère le fichier binaire exécutable ainsi que le fichier de métadonnées .winmd.  
  
 \/WINMD:NO  
 L'éditeur de liens génère uniquement le fichier binaire exécutable, mais pas un fichier .winmd.  
  
 \/WINMD:ONLY  
 L'éditeur de liens génère uniquement le fichier .winmd, mais pas le fichier binaire exécutable.  
  
 Par défaut, le nom du fichier de sortie se présente sous la forme `binaryname`.winmd.  Pour spécifier un nom de fichier différent, utilisez l'option [\/WINMDFILE](../../build/reference/winmdfile-specify-winmd-file.md) .  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Sélectionnez le dossier **Éditeur de liens**.  
  
3.  Sélectionnez la page de propriétés **Métadonnées Windows**.  
  
4.  Dans la zone de liste déroulante **Générer des métadonnées Windows**, sélectionnez l'option désirée.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)