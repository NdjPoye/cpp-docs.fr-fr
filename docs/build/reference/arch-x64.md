---
title: "/arch (x64) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: ecda22bf-5bed-43f4-99fb-88aedd83d9d8
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /arch (x64)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie l'architecture pour la génération de code sur x64.  Consultez également [\/arch \(x86\)](../../build/reference/arch-x86.md) et [\/arch \(ARM\)](../../build/reference/arch-arm.md).  
  
## Syntaxe  
  
```  
/arch:[AVX|AVX2]  
```  
  
## Arguments  
 **\/arch:AVX**  
 Active l'utilisation des instructions Intel Advanced Vector Extensions.  
  
 **\/arch:AVX2**  
 Active l'utilisation des instructions Intel Advanced Vector Extensions 2.  
  
## Notes  
 **\/arch** affecte uniquement la génération de code pour les fonctions natives.  Lorsque vous utilisez [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) pour compiler, **\/arch** n'a aucun effet sur la génération de code pour les fonctions managées.  
  
 Le symbole de préprocesseur `__AVX__` est défini quand l'option de compilateur **\/arch:AVX** est spécifiée.  Le symbole de préprocesseur `__AVX2__` est défini quand l'option de compilateur **\/arch:AVX2** est spécifiée.  Pour plus d'informations, consultez [Macros prédéfinies](../../preprocessor/predefined-macros.md).  L'option **\/arch:AVX2** a été introduite pour la première fois dans Visual Studio 2013 Update 2, version 12.0.34567.1.  
  
### Pour définir l'option de compilateur \/arch:AVX ou \/arch:AVX2 dans Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriétés** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Sélectionnez le dossier **Propriétés de configuration**, **C\/C\+\+**.  
  
3.  Sélectionnez la page de propriétés **Génération de code**.  
  
4.  Dans la zone de liste déroulante **Activation du jeu d'instructions amélioré**, choisissez **Advanced Vector Extensions \(\/arch:AVX\)** ou **Advanced Vector Extensions 2 \(\/arch:AVX2\)**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>.  
  
## Voir aussi  
 [\/arch \(Architecture d'UC minimale\)](../../build/reference/arch-minimum-cpu-architecture.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)