---
title: "/MIDL (Sp&#233;cification d&#39;options de ligne de commande MIDL) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/midl"
  - "VC.Project.VCLinkerTool.MidlCommandFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MIDL (option de l'éditeur de liens)"
  - "MIDL"
  - "MIDL (option de l'éditeur de liens)"
  - "-MIDL (option de l'éditeur de liens)"
  - "MIDL, options de ligne de commande"
ms.assetid: 22dc259e-b34c-4ed3-a380-4beb734482c1
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /MIDL (Sp&#233;cification d&#39;options de ligne de commande MIDL)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MIDL:@file  
```  
  
## Notes  
 où :  
  
 `file`  
 désigne le nom du fichier contenant les [options de ligne de commande MIDL](http://msdn.microsoft.com/library/windows/desktop/aa366839).  
  
## Notes  
 Toutes les options de conversion d'un fichier IDL en TLB doivent être indiquées dans l'argument `file` ; les options de ligne de commande MIDL ne peuvent être spécifiées sur la ligne de commande de l'éditeur de liens.  Si l'option \/MIDL n'est pas spécifiée, le compilateur MIDL sera appelé avec le nom de fichier IDL uniquement, sans aucune autre option.  
  
 Le fichier doit contenir une option de ligne de commande MIDL par ligne.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **IDL incorporé**.  
  
4.  Modifiez la propriété **Commandes MIDL**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MidlCommandFile%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)   
 [\/IDLOUT \(Nommer les fichiers de sortie MIDL\)](../../build/reference/idlout-name-midl-output-files.md)   
 [\/IGNOREIDL \(Ne pas traiter les attributs dans MIDL\)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)   
 [\/TLBOUT \(Nommer le fichier .TLB\)](../../build/reference/tlbout-name-dot-tlb-file.md)   
 [Building an Attributed Program](../../windows/building-an-attributed-program.md)