---
title: "/Zs (Contr&#244;ler la syntaxe uniquement) | Microsoft Docs"
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
  - "/zs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zs (option du compilateur C++)"
  - "vérification de la syntaxe uniquement (option du compilateur)"
  - "Zs (option du compilateur)"
  - "-Zs (option du compilateur C++)"
ms.assetid: b4b41e6a-3f41-4d09-9cb6-fde5aa2cfecf
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Zs (Contr&#244;ler la syntaxe uniquement)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Indique au compilateur de vérifier uniquement la syntaxe des fichiers source sur la ligne de commande.  
  
## Syntaxe  
  
```  
/Zs  
```  
  
## Notes  
 Lors de l'utilisation de cette option, aucun fichier de sortie n'est créé, et les messages d'erreur sont écrits dans la sortie standard.  
  
 L'option **\/Zs** offre un moyen rapide de retrouver et de corriger les erreurs de syntaxe avant la compilation et l'édition des liens d'un fichier source.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Ligne de commande**.  
  
4.  Spécifiez l'option du compilateur dans la zone **Options supplémentaires**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)