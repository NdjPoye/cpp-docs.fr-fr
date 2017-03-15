---
title: "/FU (Nom du fichier #using impos&#233;) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.ForcedUsingFiles"
  - "/FU"
  - "VC.Project.VCNMakeTool.ForcedUsingAssemblies"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FU (option du compilateur C++)"
  - "FU (option du compilateur C++)"
  - "-FU (option du compilateur C++)"
ms.assetid: 698f8603-457f-435a-baff-5ac9243d6ca1
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /FU (Nom du fichier #using impos&#233;)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une option du compilateur que vous pouvez utiliser en tant qu'alternative au passage d'un nom de fichier à [\#using, directive](../../preprocessor/hash-using-directive-cpp.md) dans le code source.  
  
## Syntaxe  
  
```  
/FU file  
```  
  
## Arguments  
 `file`  
 Spécifie les métadonnées à référencer dans cette compilation.  
  
## Notes  
 Le commutateur \/FU prend uniquement un nom de fichier.  Pour spécifier plusieurs fichiers, utilisez \/FU avec chacun d'entre eux.  
  
 Si vous utilisez [!INCLUDE[cppcli](../../build/reference/includes/cppcli_md.md)] et référencez des métadonnées pour utiliser la fonctionnalité de [Assemblys friends](../../dotnet/friend-assemblies-cpp.md), vous ne pouvez pas utiliser **\/FU**.  Vous devez référencer les métadonnées en code à l'aide de `#using`— définie avec l'attribut `[as friend]`.  Les assemblys Friends ne sont pas pris en charge dans [!INCLUDE[cppwrt](../../build/reference/includes/cppwrt_md.md)] \([!INCLUDE[cppwrt_short](../../build/reference/includes/cppwrt_short_md.md)]\).  
  
 Pour plus d'informations sur la façon de créer un assembly ou un module pour le Common Language Runtime \(CLR\), consultez [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md).  Pour plus d'informations sur la création dans un [!INCLUDE[cppwrt_short](../../build/reference/includes/cppwrt_short_md.md)], consultez [Génération d'applications et de bibliothèques](../Topic/Building%20apps%20and%20libraries%20\(C++-CX\).md).  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Sélectionnez le dossier **C\/C\+\+**.  
  
3.  Sélectionnez la page de propriétés **Avancé**.  
  
4.  Modifiez la propriété **Fichiers \#using forcés**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedUsingFiles%2A>.  
  
## Voir aussi  
 [Options du fichier de sortie \(\/F\)](../../build/reference/output-file-f-options.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)