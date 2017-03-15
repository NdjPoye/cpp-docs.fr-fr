---
title: "/ASSEMBLYLINKRESOURCE (Lien vers une ressource du .NET Framework) | Microsoft Docs"
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
  - "/ASSEMBLYLINKRESOURCE"
  - "VC.Project.VCLinkerTool.AssemblyLinkResource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ASSEMBLYLINKRESOURCE (option de l'éditeur de liens)"
  - "ASSEMBLYLINKRESOURCE (option de l'éditeur de liens)"
  - "-ASSEMBLYLINKRESOURCE (option de l'éditeur de liens)"
ms.assetid: 8b6ad184-1b33-47a4-8513-4803cf915b64
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /ASSEMBLYLINKRESOURCE (Lien vers une ressource du .NET Framework)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ASSEMBLYLINKRESOURCE:filename  
```  
  
## Notes  
 où :  
  
 *filename*  
 Fichier de ressources .NET Framework avec lequel vous voulez établir un lien à partir de l'assembly.  
  
## Notes  
 L'option \/ASSEMBLYLINKRESOURCE crée un lien à une ressource .NET Framework dans le fichier de sortie ; le fichier de ressources n'est pas placé dans l'assembly de sortie.  [\/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md) incorpore un fichier de ressources dans le fichier de sortie.  
  
 Les ressources liées sont publiques dans l'assembly lorsqu'elles sont créées avec l'éditeur de liens.  
  
 \/ASSEMBLYLINKRESOURCE impose que la compilation inclue [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) ; [\/LN](../../build/reference/ln-create-msil-module.md) ; pour que [\/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md) soit autorisé avec \/ASSEMBLYLINKRESOURCE.  
  
 Si *filename* est un fichier de ressources .NET Framework créé, par exemple, par [Resgen.exe](../Topic/Resgen.exe%20\(Resource%20File%20Generator\).md) ou dans l'environnement de développement, il est accessible avec ses membres dans l'espace de noms **System.Resources**.  Pour plus d'informations, consultez [System.Resources.ResourceManager](https://msdn.microsoft.com/en-us/library/system.resources.resourcemanager.aspx).  Pour toutes les autres ressources, utilisez les méthodes **GetManifestResource**\* de la classe **System.Reflection.Assembly** pour accéder à la ressource au moment de l'exécution.  
  
 *filename* peut avoir n'importe quel format de fichier.  Par exemple, vous pouvez décider d'intégrer une DLL native dans l'assembly : ainsi, elle pourra être installée dans le Global Assembly Cache et sera accessible depuis le code managé de l'assembly.  
  
 Les autres options de l'éditeur de liens décrites ci\-après affectent la génération de l'assembly :  
  
-   [\/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [\/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [\/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
-   [\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [\/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Ligne de commande**.  
  
4.  Tapez l'option dans la zone **Options supplémentaires**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)