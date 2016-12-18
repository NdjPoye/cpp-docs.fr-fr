---
title: "/U, /u (Annuler la d&#233;finition de symboles) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.UndefinePreprocessorDefinitions"
  - "VC.Project.VCCLWCECompilerTool.UndefinePreprocessorDefinitions"
  - "VC.Project.VCCLCompilerTool.UndefineAllPreprocessorDefinitions"
  - "/u"
  - "VC.Project.VCCLWCECompilerTool.UndefineAllPreprocessorDefinitions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/U (option du compilateur C++)"
  - "U (option du compilateur C++)"
  - "-U (option du compilateur C++)"
  - "annuler la définition de symboles (option du compilateur)"
ms.assetid: 7bc0474f-6d1f-419b-807d-0d8816763b2a
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /U, /u (Annuler la d&#233;finition de symboles)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'option du compilateur **\/U** annule la définition du symbole de préprocesseur spécifié.  L'option du compilateur **\/u** annule la définition des symboles spécifiques à Microsoft que le compilateur définit.  
  
## Syntaxe  
  
```  
/U[ ]symbol  
/u  
```  
  
## Arguments  
 `symbol`  
 Symbole de préprocesseur à ne plus définir.  
  
## Notes  
 Ni l'option **\/U**, ni **\/u** peut annuler la définition d'un symbole créé à l'aide de la directive **\#define**.  
  
 L'option **\/U** peut annuler la définition d'un symbole défini précédemment à l'aide de l'option **\/D**.  
  
 Par défaut, le compilateur définit les symboles spécifiques à Microsoft suivants.  
  
|Symbole|Fonction|  
|-------------|--------------|  
|\_CHAR\_UNSIGNED|Le type char par défaut est non signé.  Défini quand l'option [\/J](../../build/reference/j-default-char-type-is-unsigned.md) est spécifiée.|  
|\_CPPRTTI|Défini pour le code compilé avec l'option [\/GR](../../build/reference/gr-enable-run-time-type-information.md).|  
|\_CPPUNWIND|Défini pour le code compilé avec l'option [\/EHsc](../../build/reference/eh-exception-handling-model.md).|  
|\_DLL|Défini quand l'option [\/MD](../../build/reference/md-mt-ld-use-run-time-library.md) est spécifiée.|  
|\_M\_IX86|Par défaut, défini à 600 pour les cibles x86.|  
|\_MSC\_VER|Pour plus d'informations, consultez [Macros prédéfinies](../../preprocessor/predefined-macros.md).|  
|\_WIN32|Défini pour les applications WIN32.  Toujours défini.|  
|\_MT|Défini quand l'option [\/MD ou \/MT](../../build/reference/md-mt-ld-use-run-time-library.md) est spécifiée.|  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Avancé**.  
  
4.  Modifiez les propriétés **Définitions de préprocesseur non définies** ou **Annulation de la définition de toutes les définitions du préprocesseur**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UndefineAllPreprocessorDefinitions%2A> ou <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UndefinePreprocessorDefinitions%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)   
 [\/J \(Type de caractère par défaut non signé\)](../../build/reference/j-default-char-type-is-unsigned.md)   
 [\/GR \(Activer les informations de type au moment de l'exécution\)](../../build/reference/gr-enable-run-time-type-information.md)   
 [\/EH \(Modèle de gestion des exceptions\)](../../build/reference/eh-exception-handling-model.md)   
 [\/MD, \/MT, \/LD \(Utiliser la bibliothèque Runtime\)](../../build/reference/md-mt-ld-use-run-time-library.md)