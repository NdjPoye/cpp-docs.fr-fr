---
title: "/KEYCONTAINER (Sp&#233;cifier un conteneur de cl&#233; pour signer un assembly) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.KeyContainer"
  - "/keycontainer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/KEYCONTAINER (option de l'éditeur de liens)"
  - "KEYCONTAINER (option de l'éditeur de liens)"
  - "-KEYCONTAINER (option de l'éditeur de liens)"
ms.assetid: 94882d12-b77a-49c7-96d0-18a31aee001e
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /KEYCONTAINER (Sp&#233;cifier un conteneur de cl&#233; pour signer un assembly)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/KEYCONTAINER:name  
```  
  
## Notes  
 où,  
  
 *name*  
 Le conteneur qui comprend la clé.  Placez la chaîne entre guillemets \(" "\) si cet argument contient un espace.  
  
## Notes  
 L'éditeur de liens crée un assembly signé en insérant une clé publique dans le manifeste d'assembly et en signant l'assembly final avec la clé privée.  Pour générer un fichier de clé, tapez [sn \-k](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md) `file` sur la ligne de commande.  **sn \-i** installe la paire de clés dans un conteneur.  
  
 Si vous compilez avec [\/LN](../../build/reference/ln-create-msil-module.md), le nom du fichier de clé est contenu dans le module et incorporé dans l'assembly qui est créé lorsque vous compilez un assembly qui inclut une référence explicite au module, via [\#using](../../preprocessor/hash-using-directive-cpp.md) ou lors d'une liaison avec [\/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md).  
  
 Vous pouvez également passer vos informations de chiffrement au compilateur avec [\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md).  Utilisez [\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md) si vous souhaitez obtenir un assembly partiellement signé.  Pour plus d'informations sur la signature d'un assembly, consultez [Assemblys de nom fort \(signature d'assembly\)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).  
  
 Les autres options de l'éditeur de liens décrites ci\-après affectent la génération de l'assembly :  
  
-   [\/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [\/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [\/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [\/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
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