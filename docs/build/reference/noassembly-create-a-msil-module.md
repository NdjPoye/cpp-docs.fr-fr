---
title: "/NOASSEMBLY (Cr&#233;er un module MSIL) | Microsoft Docs"
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
  - "/NOASSEMBLY"
  - "VC.Project.VCLinkerTool.TurnOffAssemblyGeneration"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/NOASSEMBLY (option de l'éditeur de liens)"
  - "assemblys (C++)"
  - "assemblys (C++), ne pas créer d'assembly"
  - "NOASSEMBLY (option de l'éditeur de liens)"
  - "-NOASSEMBLY (option de l'éditeur de liens)"
ms.assetid: 3cea4e70-f451-4395-a626-1930b1b127fe
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /NOASSEMBLY (Cr&#233;er un module MSIL)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/NOASSEMBLY  
```  
  
## Notes  
 L'option \/NOASSEMBLY indique à l'Éditeur de liens de créer une image du fichier de sortie actif sans générer un assembly .NET Framework.  Un fichier de sortie MSIL dépourvu de manifeste d'assembly est appelé module.  
  
 Par défaut, un assembly est créé.  Vous pouvez également utiliser l'option du compilateur [\/LN \(Créer le module MSIL\)](../../build/reference/ln-create-msil-module.md) pour créer un module.  
  
 Les autres options de l'éditeur de liens décrites ci\-après affectent la génération de l'assembly :  
  
-   [\/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [\/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [\/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [\/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Avancé**.  
  
4.  Modifiez la propriété **Désactivation de la génération de l'assembly**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TurnOffAssemblyGeneration%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)