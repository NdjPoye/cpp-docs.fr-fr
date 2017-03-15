---
title: "/arch (ARM) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 4f1406ff-f174-487c-a126-8ab06cf447c1
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# /arch (ARM)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie l'architecture pour la génération de code sur ARM.  Consultez également [\/arch \(x86\)](../../build/reference/arch-x86.md) et [\/arch \(x64\)](../../build/reference/arch-x64.md).  
  
## Syntaxe  
  
```  
/arch:[ARMv7VE|VFPv4]  
```  
  
## Arguments  
 **\/arch:ARMv7VE**  
 Permet l'utilisation des instructions des extensions de virtualisation ARMv7VE.  
  
 **\/arch:VFPv4**  
 Permet l'utilisation des instructions ARM VFPv4.  Si cette option n'est pas spécifiée, VFPv3 est utilisé par défaut.  
  
## Notes  
 La macro `_M_ARM_FP` \(pour ARM uniquement\) indique quelle option de compilateur **\/arch** a été utilisée, le cas échéant.  Pour plus d'informations, consultez [Macros prédéfinies](../../preprocessor/predefined-macros.md).  
  
 Lorsque vous utilisez [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) pour compiler, **\/arch** n'a aucun effet sur la génération de code pour les fonctions managées.  **\/arch** affecte uniquement la génération de code pour les fonctions natives.  
  
### Pour définir l'option de compilateur \/arch:ARMv7VE ou \/arch:VFPv4 dans Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriétés** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Sélectionnez le dossier **C\/C\+\+**.  
  
3.  Sélectionnez la page de propriétés **Ligne de commande**.  
  
4.  Dans la zone **Options supplémentaires**, ajoutez `/arch:ARMv7VE` ou `/arch:VFPv4`.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>.  
  
## Voir aussi  
 [\/arch \(Architecture d'UC minimale\)](../../build/reference/arch-minimum-cpu-architecture.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)