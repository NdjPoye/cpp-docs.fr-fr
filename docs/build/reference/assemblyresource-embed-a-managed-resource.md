---
title: "/ASSEMBLYRESOURCE (Incorporer une ressource manag&#233;e) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.EmbedManagedResourceFile"
  - "/ASSEMBLYRESOURCE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ASSEMBLYRESOURCE (option de l'éditeur de liens)"
  - "assemblys (C++)"
  - "assemblys (C++), lier des fichiers de ressources"
  - "ASSEMBLYRESOURCE (option de l'éditeur de liens)"
  - "-ASSEMBLYRESOURCE (option de l'éditeur de liens)"
ms.assetid: 0ce6e1fb-921b-4b1b-a59c-d35388d789f2
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /ASSEMBLYRESOURCE (Incorporer une ressource manag&#233;e)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ASSEMBLYRESOURCE:filename[,[name][,PRIVATE]]  
```  
  
## Paramètres  
 *filename*  
 désigne la ressource managée que vous souhaitez incorporer à cet assembly.  
  
 *name*  
 Optionnel.  Nom logique de la ressource, c'est\-à\-dire le nom utilisé pour charger cette dernière.  La valeur par défaut est le nom du fichier.  
  
 Si vous le souhaitez, vous pouvez spécifier si le fichier doit être privé dans le manifeste d'assembly.  Par défaut, *name* est public dans l'assembly.  
  
## Notes  
 Utilisez l'option \/ASSEMBLYRESOURCE pour incorporer une ressource dans un assembly.  
  
 Les ressources sont publiques dans l'assembly lorsqu'elles sont créées avec l'éditeur de liens.  L'éditeur de liens ne vous permet pas de renommer la ressource dans l'assembly.  
  
 Si *filename* est un fichier de ressources .NET Framework \(.resources\) créé, par exemple, par l'[outil Resource File Generator Tool \(Resgen.exe\)](../Topic/Resgen.exe%20\(Resource%20File%20Generator\).md) ou dans l'environnement de développement, il est accessible avec ses membres dans l'espace de noms **System.Resources** \(consultez [System.Resources.ResourceManager](https://msdn.microsoft.com/en-us/library/system.resources.resourcemanager.aspx) pour plus d'informations\).  Pour toutes les autres ressources, utilisez les méthodes **GetManifestResource**\* de la classe **System.Reflection.Assembly** pour accéder à la ressource au moment de l'exécution.  
  
 Les autres options de l'éditeur de liens décrites ci\-après affectent la génération de l'assembly :  
  
-   [\/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [\/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [\/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
-   [\/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Entrée**.  
  
4.  Modifiez la propriété **Incorporation du fichier de ressources managé**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EmbedManagedResourceFile%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)