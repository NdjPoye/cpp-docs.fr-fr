---
title: "/IDLOUT (Nommer les fichiers de sortie MIDL) | Microsoft Docs"
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
  - "/idlout"
  - "VC.Project.VCLinkerTool.MergedIDLBaseFileName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fichiers .idl, chemin"
  - "/IDLOUT (option de l'éditeur de liens)"
  - "fichiers IDL, chemin"
  - "IDLOUT (option de l'éditeur de liens)"
  - "-IDLOUT (option de l'éditeur de liens)"
  - "MIDL"
  - "MIDL, noms de fichiers de sortie"
ms.assetid: 10d00a6a-85b4-4de1-8732-e422c6931509
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /IDLOUT (Nommer les fichiers de sortie MIDL)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/IDLOUT:[path\]filename  
```  
  
## Paramètres  
 *path*  
 désigne une spécification de chemin d'accès absolu ou relatif.  En spécifiant un chemin d'accès, vous affectez uniquement l'emplacement d'un fichier .idl ; tous les autres fichiers sont placés dans le répertoire du projet.  
  
 *filename*  
 Spécifie le nom du fichier .idl créé par le compilateur MIDL.  Aucune extension de fichier particulière n'est demandée ; spécifiez *filename*.idl si vous souhaitez une extension .idl.  
  
## Notes  
 L'option \/IDLOUT spécifie le nom et l'extension du fichier .idl.  
  
 Le compilateur MIDL est appelé par l'éditeur de liens Visual C\+\+ lors de la liaison de projets dotés de l'attribut [module](../../windows/module-cpp.md).  
  
 L'option \/IDLOUT spécifie également les noms de fichiers des autres fichiers de sortie associés au compilateur MIDL :  
  
-   *filename*.tlb  
  
-   *filename*\_p.c  
  
-   *filename*\_i.c  
  
-   *filename*.h  
  
 *filename* est le paramètre que vous passez à \/IDLOUT.  Si [\/TLBOUT](../../build/reference/tlbout-name-dot-tlb-file.md) est spécifié, le fichier .tlb obtiendra son nom de \/TLBOUT *filename*.  
  
 Que vous spécifiiez \/IDLOUT ou \/TLBOUT, l'éditeur de liens crée vc70.tlb, vc70.idl, vc70\_p.c, vc70\_i.c et vc70.h.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **IDL incorporé**.  
  
4.  Modifiez la propriété **Nom de fichier de base IDL fusionné**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergedIDLBaseFileName%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)   
 [\/IGNOREIDL \(Ne pas traiter les attributs dans MIDL\)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)   
 [\/MIDL \(Spécification d'options de ligne de commande MIDL\)](../../build/reference/midl-specify-midl-command-line-options.md)   
 [Building an Attributed Program](../../windows/building-an-attributed-program.md)