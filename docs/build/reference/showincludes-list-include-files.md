---
title: "/showIncludes (Liste des fichiers Include) | Microsoft Docs"
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
  - "VC.Project.VCCLWCECompilerTool.ShowIncludes"
  - "VC.Project.VCCLCompilerTool.ShowIncludes"
  - "/showincludes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/showIncludes (option du compilateur C++)"
  - "fichiers Include"
  - "fichiers Include, afficher dans la compilation"
  - "showIncludes (option du compilateur C++)"
  - "-showIncludes (option du compilateur C++)"
ms.assetid: 0b74b052-f594-45a6-a7c7-09e1a319547d
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /showIncludes (Liste des fichiers Include)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Demande au compilateur de produire la liste des fichiers Include.  Les fichiers Include imbriqués sont également affichés \(les fichiers qui sont inclus à partir des fichiers que vous incluez\).  
  
## Syntaxe  
  
```  
/showIncludes  
```  
  
## Notes  
 Quand un fichier Include est rencontré pendant la compilation, un message est émis, par exemple :  
  
```  
Note: including file: d:\MyDir\include\stdio.h  
```  
  
 Les fichiers Include imbriqués sont indiqués par une mise en retrait, un espace pour chaque niveau d'imbrication. Par exemple :  
  
```  
Note: including file: d:\temp\1.h  
Note: including file:  d:\temp\2.h  
```  
  
 Dans ce cas, `2.h` a été inclus à partir de `1.h`, d'où la mise en retrait.  
  
 L'option **\/showIncludes** est émise vers `stderr`, et non vers `stdout`.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Avancé**.  
  
4.  Modifiez la propriété **Affichage des fichiers Include**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ShowIncludes%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)