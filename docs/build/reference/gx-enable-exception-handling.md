---
title: "/GX (Activer la gestion des exceptions) | Microsoft Docs"
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
  - "/gx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/GX (option du compilateur C++)"
  - "compilateur cl.exe, gestion des exceptions"
  - "activer la gestion des exceptions (option du compilateur C++)"
  - "gestion des exceptions, activer"
  - "GX (option du compilateur C++)"
  - "-GX (option du compilateur C++)"
ms.assetid: 933b43ba-de77-4ff8-a48b-7074de90bc1c
caps.latest.revision: 16
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /GX (Activer la gestion des exceptions)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Active la gestion synchrone des exceptions en partant du principe que les fonctions C `extern` ne lèvent jamais d'exception.  
  
## Syntaxe  
  
```  
/GX  
```  
  
## Notes  
 Équivaut à [\/EH \(Modèle de gestion des exceptions\)](../../build/reference/eh-exception-handling-model.md).  
  
 L'option **\/GX** est activée, par défaut, quand vous compilez à partir de l'environnement de développement.  Par défaut, l'option **\/GX\-** est activée lors de l'utilisation d'outils de ligne de commande.  
  
 Pour plus d'informations, consultez [Gestion d'exceptions C\+\+](../../cpp/cpp-exception-handling.md).  
  
 **\/GX** est déconseillé ; utilisation de [\/EH \(Modèle de gestion des exceptions\)](../../build/reference/eh-exception-handling-model.md) à la place.  Pour plus d'informations, consultez [Deprecated Compiler Options in Visual C\+\+ 2005](http://msdn.microsoft.com/fr-fr/aa59fce3-50b8-4f66-9aeb-ce09a7a84cce).  
  
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