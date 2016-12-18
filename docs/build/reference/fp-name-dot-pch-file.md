---
title: "/Fp (Nom de fichier .pch) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.PrecompiledHeaderFile"
  - "/fp"
  - "VC.Project.VCCLWCECompilerTool.PrecompiledHeaderFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fichiers .pch, affecter des noms"
  - "/Fp (option du compilateur C++)"
  - "Fp (option du compilateur C++)"
  - "-Fp (option du compilateur C++)"
  - "noms (C++), PCH"
  - "nommer des fichiers d'en-tête précompilés"
  - "fichiers PCH, affecter des noms"
  - "fichiers d'en-tête précompilés, affecter des noms"
ms.assetid: 0fcd9cbd-e09f-44d3-9715-b41efb5d0be2
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Fp (Nom de fichier .pch)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit un nom de chemin d'accès pour un en\-tête précompilé plutôt que d'utiliser le nom de chemin d'accès par défaut.  
  
## Syntaxe  
  
```  
/Fppathname  
```  
  
## Notes  
 Utilisez cette option avec [\/Yc \(Créer un fichier d'en\-tête précompilé\)](../../build/reference/yc-create-precompiled-header-file.md) ou [\/Yu \(Utiliser un fichier d'en\-tête précompilé\)](../../build/reference/yu-use-precompiled-header-file.md) en vue de fournir un nom de chemin d'accès pour un en\-tête précompilé à la place du nom de chemin d'accès par défaut.  Vous pouvez également utiliser **\/Fp** avec **\/Yc** pour spécifier l'utilisation d'un fichier d'en\-tête précompilé qui diffère de l'argument **\/Yc** `filename` et du nom de base du fichier source.  
  
 Si vous ne spécifiez pas une extension dans le nom de chemin d'accès, l'extension .pch s'applique par défaut.  Si vous spécifiez un répertoire sans nom de fichier, le nom de fichier par défaut est VC`x`0.pch., où `x` est la version principale de Visual C\+\+ en cours d'utilisation.  
  
 Vous pouvez aussi utiliser l'option **\/Fp** avec **\/Yu**.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **En\-têtes précompilés**.  
  
4.  Modifiez la propriété **Fichier d'en\-tête précompilé**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderFile%2A>.  
  
## Exemple  
 Si vous souhaitez créer un fichier d'en\-tête précompilé pour une version de débogage de votre programme et si vous compilez à la fois des fichiers d'en\-tête et du code source, vous pouvez spécifier une commande, telle que :  
  
```  
CL /DDEBUG /Zi /Yc /FpDPROG.PCH PROG.CPP  
```  
  
## Exemple  
 La commande suivante spécifie l'utilisation d'un fichier d'en\-tête précompilé nommé MYPCH.pch.  Le compilateur part du principe que le code source figurant dans PROG.cpp a été précompilé par MYAPP.h et que le code précompilé réside dans MYPCH.pch.  Il utilise le contenu de MYPCH.pch et compile le reste de PROG.cpp pour créer un fichier .obj.  La sortie de cet exemple est un fichier nommé PROG.exe.  
  
```  
CL /YuMYAPP.H /FpMYPCH.PCH PROG.CPP  
```  
  
## Voir aussi  
 [Options du fichier de sortie \(\/F\)](../../build/reference/output-file-f-options.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)   
 [Spécification du nom de chemin](../../build/reference/specifying-the-pathname.md)