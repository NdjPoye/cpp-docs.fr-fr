---
title: "/GH (Activer la fonction de raccordement _pexit) | Microsoft Docs"
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
  - "_pexit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Gh (option du compilateur C++)"
  - "_pexit (fonction)"
  - "Gh (option du compilateur C++)"
  - "-Gh (option du compilateur C++)"
ms.assetid: 93181453-2676-42e5-bf63-3b19e07299b6
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /GH (Activer la fonction de raccordement _pexit)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Appelle la fonction `_pexit` à la fin de chaque méthode ou fonction.  
  
## Syntaxe  
  
```  
/GH  
```  
  
## Notes  
 La fonction `_pexit` ne fait partie d'aucune bibliothèque et c'est à vous de fournir une définition pour `_pexit`.  
  
 Sauf si vous envisagez d'appeler explicitement `_pexit`, vous n'avez pas besoin de fournir un prototype.  La fonction doit apparaître comme si elle avait le prototype suivant, et elle doit exécuter un push sur le contenu de tous les registres à l'entrée et un pop sur le contenu non modifié à la sortie :  
  
```  
void __declspec(naked) _cdecl _pexit( void );  
```  
  
 `_pexit` est similaire à `_penter` ; consultez [\/Gh \(Activer la fonction de raccordement \_penter\)](../../build/reference/gh-enable-penter-hook-function.md) pour obtenir un exemple de la manière d'écrire une fonction `_pexit`.  
  
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