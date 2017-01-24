---
title: "/Ge (Activer les tests de pile) | Microsoft Docs"
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
  - "/ge"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Ge (option du compilateur C++)"
  - "activer les tests de pile"
  - "Ge (option du compilateur C++)"
  - "-Ge (option du compilateur C++)"
  - "appels de contrôle de pile"
  - "tests de pile"
  - "pile, tests de pile"
ms.assetid: 4b54deae-4e3c-4bfa-95f3-ba23590f7258
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Ge (Activer les tests de pile)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Active les tests de pile pour chaque appel de fonction qui requiert un stockage pour des variables locales.  
  
## Syntaxe  
  
```  
/Ge  
```  
  
## Notes  
 Ce mécanisme est utile si vous réécrivez la fonctionnalité de test de pile.  Il est recommandé d'utiliser [\/Gh \(Activer la fonction de raccordement \_penter\)](../../build/reference/gh-enable-penter-hook-function.md) de préférence à la réécriture du test de pile.  
  
 [\/Gs \(contrôler les appels de contrôle de pile\)](../../build/reference/gs-control-stack-checking-calls.md) a le même effet.  
  
 **\/Ge** est déconseillé ; le compilateur génère le contrôle de pile.  Pour plus d'informations, consultez [Deprecated Compiler Options in Visual C\+\+ 2005](http://msdn.microsoft.com/fr-fr/aa59fce3-50b8-4f66-9aeb-ce09a7a84cce).  
  
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