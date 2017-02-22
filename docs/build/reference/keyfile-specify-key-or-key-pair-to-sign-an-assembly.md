---
title: "/KEYFILE (Sp&#233;cifier une cl&#233; ou une paire de cl&#233;s pour signer un assembly) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/keyfile"
  - "VC.Project.VCLinkerTool.KeyFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/KEYFILE (option de l'éditeur de liens)"
  - "KEYFILE (option de l'éditeur de liens)"
  - "-KEYFILE (option de l'éditeur de liens)"
ms.assetid: 9b71f8c0-541c-4fe5-a0c7-9364f42ecb06
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /KEYFILE (Sp&#233;cifier une cl&#233; ou une paire de cl&#233;s pour signer un assembly)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/KEYFILE:filename  
```  
  
## Notes  
 où :  
  
 *filename*  
 Le fichier qui comprend la clé.  Placez la chaîne entre guillemets \(" "\) si cet argument contient un espace.  
  
## Notes  
 L'éditeur de liens insère la clé publique dans le manifeste d'assembly, puis signe l'assembly final avec la clé privée.  Pour générer un fichier de clé, tapez [sn \-k](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md) `file` sur la ligne de commande.  Un assembly signé est réputé porter un nom fort.  
  
 Si vous compilez avec [\/LN](../../build/reference/ln-create-msil-module.md), le nom du fichier de clé est contenu dans le module et incorporé dans l'assembly qui est créé lorsque vous compilez un assembly qui inclut une référence explicite au module, via [\#using](../../preprocessor/hash-using-directive-cpp.md) ou lors d'une liaison avec [\/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md).  
  
 Vous pouvez également passer vos informations de chiffrement à l'éditeur de liens avec [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md).  Utilisez [\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md) si vous souhaitez obtenir un assembly partiellement signé.  Pour plus d'informations sur la signature d'un assembly, consultez [Assemblys de nom fort \(signature d'assembly\)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).  
  
 Si **\/KEYFILE** et **\/KEYCONTAINER** sont tous deux spécifiés \(par une option de ligne de commande ou par un attribut personnalisé\), l'éditeur de liens tente d'abord le conteneur de clé.  Si cette tentative aboutit, l'assembly est signé avec les informations figurant dans le conteneur de clé.  Si l'éditeur de liens ne trouve pas le conteneur de clé, il tente le fichier spécifié avec \/KEYFILE.  Si cette tentative aboutit, l'assembly est signé avec les informations du fichier de clé et les informations de clé sont installées dans le conteneur de clé \(résultat similaire à celui de sn \-i\) afin que, lors de la prochaine compilation, le conteneur de clé soit valide.  
  
 Notez qu'un fichier de clé pourrait contenir uniquement la clé publique.  
  
 Consultez [Création et utilisation d'assemblys avec nom fort](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md) pour plus d'informations sur la signature d'un assembly.  
  
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