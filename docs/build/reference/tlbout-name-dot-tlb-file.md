---
title: "/TLBOUT (Nommer le fichier .TLB) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.TypeLibraryFile"
  - "/tlbout"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fichiers .tlb, renommer"
  - "/TLBOUT (option de l'éditeur de liens)"
  - "fichiers tlb, renommer"
  - "TLBOUT (option de l'éditeur de liens)"
  - "-TLBOUT (option de l'éditeur de liens)"
ms.assetid: 0df6d078-2e48-46c9-a1a5-02674d85dce8
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /TLBOUT (Nommer le fichier .TLB)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/TLBOUT:[path\]filename  
```  
  
## Notes  
 où :  
  
 *path*  
 désigne une spécification de chemin d'accès absolu ou relatif concernant l'emplacement de création du fichier .tlb.  
  
 *filename*  
 Spécifie le nom du fichier .tlb créé par le compilateur MIDL.  Aucune extension de fichier particulière n'est demandée ; spécifiez *filename*.tlb si vous souhaitez une extension .tlb.  
  
## Notes  
 L'option \/TLBOUT spécifie le nom et l'extension du fichier .tlb.  
  
 Le compilateur MIDL est appelé par l'éditeur de liens Visual C\+\+ lors de la liaison de projets dotés de l'attribut [module](../../windows/module-cpp.md).  
  
 Si \/TLBOUT n'est pas spécifié, le fichier .tlb obtiendra son nom de [\/IDLOUT](../../build/reference/idlout-name-midl-output-files.md) *filename*.  Si \/IDLOUT n'est pas spécifié, le fichier .tlb s'appellera vc70.tlb.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **IDL incorporé**.  
  
4.  Modifiez la propriété **Bibliothèque de types**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryFile%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)   
 [\/IGNOREIDL \(Ne pas traiter les attributs dans MIDL\)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)   
 [\/MIDL \(Spécification d'options de ligne de commande MIDL\)](../../build/reference/midl-specify-midl-command-line-options.md)   
 [Building an Attributed Program](../../windows/building-an-attributed-program.md)