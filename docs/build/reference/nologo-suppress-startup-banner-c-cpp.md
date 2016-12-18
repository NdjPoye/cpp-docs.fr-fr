---
title: "/nologo (Suppression de la banni&#232;re de d&#233;marrage) (C/C++) | Microsoft Docs"
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
  - "VC.Project.VCCLWCECompilerTool.SuppressStartupBanner"
  - "VC.Project.VCCLCompilerTool.SuppressStartupBanner"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/nologo (option du compilateur C++)"
  - "bannières, supprimer au démarrage"
  - "nologo (option du compilateur C++)"
  - "-nologo (option du compilateur C++)"
ms.assetid: 75930d8b-b11c-4db8-99e5-b52f97da0693
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /nologo (Suppression de la banni&#232;re de d&#233;marrage) (C/C++)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Supprime l'affichage de la bannière de copyright lorsque le compilateur démarre et affiche des messages d'information pendant la compilation.  
  
## Syntaxe  
  
```  
/nologo  
```  
  
## Notes  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Général**.  
  
4.  Modifiez la propriété **Suppression de la bannière de démarrage**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.SuppressStartupBanner%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)