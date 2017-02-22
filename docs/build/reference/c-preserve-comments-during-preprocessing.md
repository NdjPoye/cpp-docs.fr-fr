---
title: "/C (Conserver les commentaires pendant le pr&#233;traitement) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.KeepComments"
  - "/c"
  - "VC.Project.VCCLWCECompilerTool.KeepComments"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/c (option du compilateur C++)"
  - "c (option du compilateur C++)"
  - "-c (option du compilateur C++)"
  - "commentaires, conserver pendant le prétraitement"
  - "conserver les commentaires pendant le prétraitement"
ms.assetid: 944567ca-16bc-4728-befe-d414a7787f26
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /C (Conserver les commentaires pendant le pr&#233;traitement)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Conserve les commentaires pendant le prétraitement.  
  
## Syntaxe  
  
```  
/C  
```  
  
## Notes  
 Cette option du compilateur exige l'option **\/E**, **\/P**ou **\/EP**.  
  
 L'exemple de code suivant affiche le commentaire du code source.  
  
```  
// C_compiler_option.cpp  
// compile with: /E /C /c  
int i;   // a variable  
```  
  
 Cet exemple produit le résultat suivant :  
  
```  
#line 1 "C_compiler_option.cpp"  
int i;   // a variable  
```  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Préprocesseur**.  
  
4.  Modifiez la propriété **Commentaires conservés**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.KeepComments%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)   
 [\/E \(Prétraiter dans stdout\)](../../build/reference/e-preprocess-to-stdout.md)   
 [\/P \(Prétraiter jusqu'à un fichier\)](../../build/reference/p-preprocess-to-a-file.md)   
 [\/EP \(Prétraiter dans stdout sans directive \#line\)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)