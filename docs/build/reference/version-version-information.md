---
title: "/VERSION (Informations de version) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.Version"
  - "/version"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/VERSION (option de l'éditeur de liens)"
  - "informations de version (option de l'éditeur de liens)"
  - "VERSION (option de l'éditeur de liens)"
  - "-VERSION (option de l'éditeur de liens)"
  - "numéros de version, spécifier dans .exe"
ms.assetid: b86d0e86-dca6-4316-aee2-d863ccb9f223
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# /VERSION (Informations de version)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/VERSION:major[.minor]  
```  
  
## Notes  
 où :  
  
 arguments *major* et *minor*  
 Numéro de version que vous souhaitez insérer dans l'en\-tête du fichier .exe ou .dll.  
  
## Notes  
 L'option \/VERSION indique à l'Éditeur de liens d'ajouter un numéro de version dans l'en\-tête du fichier .exe ou .dll.  Utilisez DUMPBIN [\/HEADERS](../../build/reference/headers.md) pour afficher le champ de version de l'image de OPTIONAL HEADER VALUES afin de constater l'effet de \/VERSION.  
  
 Les arguments *major* et *minor* sont des nombres décimaux compris entre 0 et 65 535.  La valeur par défaut correspond à la version 0.0.  
  
 Les informations spécifiées avec \/VERSION n'affectent pas les informations de version qui apparaissent pour une application lorsque vous affichez ses propriétés dans l'Explorateur de fichiers.  Ces informations proviennent d'un fichier de ressources utilisé pour générer l'application.  Pour plus d'informations, consultez [Éditeur d'informations sur la version](../../mfc/version-information-editor.md).  
  
 Vous pouvez spécifier un numéro de version d'une manière équivalente à l'aide de l'instruction de définition de module [VERSION](../../build/reference/version-c-cpp.md).  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Général**.  
  
4.  Modifiez la propriété **Version**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Version%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)