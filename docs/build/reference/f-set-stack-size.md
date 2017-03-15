---
title: "/F (D&#233;finir la taille de pile) | Microsoft Docs"
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
  - "/f"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/F (option du compilateur C++)"
  - "F (option du compilateur C++)"
  - "-F (option du compilateur C++)"
  - "définir la taille de la pile (option du compilateur)"
  - "pile, définir la taille"
ms.assetid: 17320b6f-8305-445b-9ec2-75833f4b29e0
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /F (D&#233;finir la taille de pile)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit la taille, en octets, de la pile du programme.  
  
## Syntaxe  
  
```  
/F number  
```  
  
## Arguments  
 `number`  
 La taille de la pile est exprimée en octets.  
  
## Notes  
 Sans cette option, la taille de la pile équivaut par défaut à 1 Mo.  L'argument `number` peut être exprimé en notation décimale ou de langage C.  L'argument peut être compris entre 1 et la taille de pile maximale acceptée par l'éditeur de liens.  L'éditeur de liens arrondit la valeur spécifiée aux 4 octets les plus proches.  L'espace entre **\/F** et `number` est facultatif.  
  
 Vous devrez peut\-être augmenter la taille de la pile si votre programme génère des messages indiquant un dépassement de capacité de la pile.  
  
 Vous pouvez également définir la taille de la pile des manières suivantes :  
  
-   À l'aide de l'option de l'éditeur de liens **\/STACK**.  Pour plus d'informations, consultez [\/STACK](../../build/reference/stack.md).  
  
-   À l'aide de EDITBIN sur le fichier .exe.  Pour plus d'informations, consultez [Référence EDITBIN](../../build/reference/editbin-reference.md).  
  
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