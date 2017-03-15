---
title: "/Y- (Ignorer les options d&#39;en-t&#234;tes pr&#233;compil&#233;s) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/y-"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Y- (option du compilateur C++)"
  - "-Y- (option du compilateur C++)"
  - "Y- (option du compilateur C++)"
ms.assetid: cfaecb36-58db-46b8-b04d-cca6072b1b7a
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /Y- (Ignorer les options d&#39;en-t&#234;tes pr&#233;compil&#233;s)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Indique que toutes les autres options du compilateur `/Y` doivent être ignorées \(et ne peut pas être substituée\).  
  
## Syntaxe  
  
```  
/Y-  
```  
  
## Notes  
 Pour plus d'informations sur les en\-têtes précompilés, consultez :  
  
-   [\/Y \(En\-têtes précompilés\)](../../build/reference/y-precompiled-headers.md)  
  
-   [Création de fichiers d'en\-tête précompilés](../../build/reference/creating-precompiled-header-files.md)  
  
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