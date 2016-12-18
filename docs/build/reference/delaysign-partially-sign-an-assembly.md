---
title: "/DELAYSIGN (Signer partiellement un assembly) | Microsoft Docs"
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
  - "/delaysign"
  - "VC.Project.VCLinkerTool.DelaySign"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DELAYSIGN (option de l'éditeur de liens)"
  - "DELAYSIGN (option de l'éditeur de liens)"
  - "-DELAYSIGN (option de l'éditeur de liens)"
ms.assetid: 15244d30-3ecb-492f-a408-ffe81f38de20
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /DELAYSIGN (Signer partiellement un assembly)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DELAYSIGN[:NO]  
```  
  
## Notes  
 où,  
  
 NO  
 Spécifie que l'assembly ne doit pas être partiellement signé.  
  
## Notes  
 Utilisez **\/DELAYSIGN** si vous souhaitez uniquement placer la clé publique dans l'assembly.  La valeur par défaut est **\/DELAYSIGN:NO**.  
  
 L'option **\/DELAYSIGN** ne produit aucun effet, sauf lorsqu'elle est utilisée avec [\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) ou [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md).  
  
 Lorsque vous demandez un assembly complètement signé, le compilateur hache le fichier contenant le manifeste \(métadonnées de l'assembly\) et signe ce hachage avec la clé privée.  La signature numérique obtenue est stockée dans le fichier qui contient le manifeste.  Lorsque la signature d'un assembly est différée, l'éditeur de liens ne calcule ni ne stocke la signature, mais réserve un espace dans le fichier pour pouvoir y ajouter ultérieurement la signature.  
  
 Par exemple, l'utilisation de **\/DELAYSIGN** permet à un testeur d'insérer l'assembly dans le cache global.  Après le test, vous pouvez signer complètement l'assembly en y plaçant la clé privée.  
  
 Pour plus d'informations sur la signature d'un assembly, consultez [Assemblys de nom fort \(signature d'assembly\)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) et [Temporisation de signature d'un assembly](../Topic/Delay%20Signing%20an%20Assembly.md).  
  
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