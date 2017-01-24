---
title: "/ASSEMBLYMODULE (Ajouter un module MSIL &#224; l&#39;assembly) | Microsoft Docs"
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
  - "/assemblymodule"
  - "VC.Project.VCLinkerTool.AddModuleNamesToAssembly"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ASSEMBLYMODULE (option de l'éditeur de liens)"
  - "assemblys (C++)"
  - "assemblys (C++), ajouter des modules aux"
  - "ASSEMBLYMODULE (option de l'éditeur de liens)"
  - "-ASSEMBLYMODULE (option de l'éditeur de liens)"
ms.assetid: 67357da8-e4b6-49fd-932c-329a5777f143
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /ASSEMBLYMODULE (Ajouter un module MSIL &#224; l&#39;assembly)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ASSEMBLYMODULE:filename  
```  
  
## Notes  
 où :  
  
 *filename*  
 est le module que vous souhaitez inclure dans cet assembly.  
  
## Notes  
 L'option \/ASSEMBLYMODULE vous permet d'ajouter une référence de module à un assembly.  Les informations de type du module ne seront pas disponibles pour le programme d'assembly ayant ajouté la référence de module.  En revanche, elles seront disponibles pour tous les programmes qui font référence à l'assembly.  
  
 Utilisez [\#using](../../preprocessor/hash-using-directive-cpp.md) pour ajouter la référence d'un module à un assembly et pour rendre les informations de type du module disponibles pour le programme d'assembly.  
  
 Observez par exemple le scénario suivant :  
  
1.  Créez un module avec [\/LN](../../build/reference/ln-create-msil-module.md).  
  
2.  Utilisez \/ASSEMBLYMODULE dans un autre projet pour inclure le module dans l'application actuelle, ce qui va créer un assembly.  Ce projet ne référencera pas le module à l'aide de `#using`.  
  
3.  Tout projet référençant cet assembly peut maintenant utiliser les types à partir du module.  
  
 Les autres options de l'éditeur de liens décrites ci\-après affectent la génération de l'assembly :  
  
-   [\/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [\/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [\/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [\/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
-   [\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
 L'éditeur de liens Visual C\+\+ reçoit des fichiers .netmodule en entrée et le fichier de sortie produit par l'éditeur de liens sera un assembly ou un .netmodule sans dépendance au moment de l'exécution sur tout .netmodules qui auraient été reliés en entrée à l'éditeur de liens.  Pour plus d'informations, consultez [Fichiers .netmodule en tant qu'entrée de l'Éditeur de liens](../../build/reference/netmodule-files-as-linker-input.md).  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Entrée**.  
  
4.  Modifiez la propriété **Ajout du module à l'assembly**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AddModuleNamesToAssembly%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)