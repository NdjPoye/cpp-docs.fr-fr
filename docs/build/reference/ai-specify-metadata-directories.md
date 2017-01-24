---
title: "/AI (Sp&#233;cifier les r&#233;pertoires des m&#233;tadonn&#233;es) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.AdditionalUsingDirectories"
  - "VC.Project.VCNMakeTool.AssemblySearchPath"
  - "/AI"
  - "VC.Project.VCCLWCECompilerTool.AdditionalUsingDirectories"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/AI (option du compilateur C++)"
  - "AI (option du compilateur C++)"
  - "-AI (option du compilateur C++)"
ms.assetid: fb9c1846-504c-4a3b-bb39-c8696de32f6f
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /AI (Sp&#233;cifier les r&#233;pertoires des m&#233;tadonn&#233;es)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie un répertoire dans lequel le compilateur doit faire une recherche en vue de résoudre les références de fichiers passées à la directive `#using`.  
  
## Syntaxe  
  
```  
/AIdirectory  
```  
  
## Arguments  
 `directory`  
 Le répertoire ou le chemin d'accès dans lequel le compilateur va effectuer la recherche.  
  
## Notes  
 Un seul répertoire peut être passé à un appel **\/AI**.  Spécifiez une option **\/AI** pour chaque chemin d'accès que le compilateur doit rechercher.  Par exemple, pour ajouter C:\\Project\\Meta et C:\\Common\\Meta au chemin de recherche du compilateur `#using`, ajoutez `/AI"C:\Project\Meta" /AI"C:\Common\Meta"` à la ligne de commande du compilateur ou ajoutez chaque répertoire à la propriété **Répertoires \#using supplémentaires** dans Visual Studio.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Dans le volet de navigation, sélectionnez **Propriétés de configuration**, **C\/C\+\+**, **Général**.  
  
3.  Modifiez la propriété **Répertoires \#using supplémentaires**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalUsingDirectories%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)   
 [\#using, directive](../../preprocessor/hash-using-directive-cpp.md)