---
title: "/vmb, /vmg (M&#233;thode de repr&#233;sentation) | Microsoft Docs"
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
  - "/vmb"
  - "/vmg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/vmb (option du compilateur C++)"
  - "/vmg (option du compilateur C++)"
  - "méthode de représentation (options du compilateur C++)"
  - "vmb (option du compilateur C++)"
  - "-vmb (option du compilateur C++)"
  - "vmg (option du compilateur C++)"
  - "-vmg (option du compilateur C++)"
ms.assetid: ecdb391c-7dab-40b1-916b-673d10889fd4
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /vmb, /vmg (M&#233;thode de repr&#233;sentation)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Permettent de sélectionner la méthode que le compilateur utilise pour représenter les pointeurs vers des membres de classe.  
  
 Utilisez **\/vmb** si vous définissez toujours une classe avant de déclarer un pointeur vers un membre de la classe.  
  
 Utilisez **\/vmg** pour déclarer un pointeur vers un membre de la classe avant de définir la classe en question.  Cette situation peut se présenter si vous définissez des membres dans deux classes différentes qui font référence l'une à l'autre.  Pour de telles classes qui se font mutuellement référence, une classe doit être référencée avant d'être définie.  
  
## Syntaxe  
  
```  
/vmb  
/vmg  
```  
  
## Notes  
 Vous pouvez également utiliser [pointers\_to\_members](../../preprocessor/pointers-to-members.md) ou [Mots clé d'héritage](../../cpp/inheritance-keywords.md) dans votre code pour spécifier une représentation de pointeur.  
  
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