---
title: "/IGNOREIDL (Ne pas traiter les attributs dans MIDL) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.IgnoreEmbeddedIDL"
  - "/ignoreidl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/IGNOREIDL (option de l'éditeur de liens)"
  - "IGNOREIDL (option de l'éditeur de liens)"
  - "-IGNOREIDL (option de l'éditeur de liens)"
ms.assetid: 29514098-6a1c-4317-af2f-1dc268972780
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /IGNOREIDL (Ne pas traiter les attributs dans MIDL)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/IGNOREIDL  
```  
  
## Notes  
 L'option \/IGNOREIDL spécifie qu'un [Attributs IDL](../../windows/idl-attributes.md) de code source ne doit pas être traité dans un fichier .idl.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **IDL incorporé**.  
  
4.  Modifiez la propriété **IDL incorporé ignoré**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreEmbeddedIDL%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)   
 [\/IDLOUT \(Nommer les fichiers de sortie MIDL\)](../../build/reference/idlout-name-midl-output-files.md)   
 [\/TLBOUT \(Nommer le fichier .TLB\)](../../build/reference/tlbout-name-dot-tlb-file.md)   
 [\/MIDL \(Spécification d'options de ligne de commande MIDL\)](../../build/reference/midl-specify-midl-command-line-options.md)   
 [Building an Attributed Program](../../windows/building-an-attributed-program.md)