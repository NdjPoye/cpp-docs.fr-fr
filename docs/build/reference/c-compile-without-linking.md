---
title: "/c (Compiler sans liaison) | Microsoft Docs"
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
  - "/c"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/c (option du compilateur C++)"
  - "c (option du compilateur C++)"
  - "-c (option du compilateur C++)"
  - "compilateur cl.exe, compiler sans édition des liens"
  - "supprimer la liaison"
ms.assetid: 8017fc3d-e5dd-4668-a1f7-3120daa95d20
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /c (Compiler sans liaison)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Empêche l'appel automatique à LINK.  
  
## Syntaxe  
  
```  
/c  
```  
  
## Notes  
 La compilation avec **\/c** crée des fichiers .obj uniquement.  Vous devez donc appeler LINK de manière explicite à l'aide des fichiers et des options appropriés pour effectuer la phase de liaison de la génération.  
  
 Tout projet interne créé dans l'environnement de développement utilise l'option **\/c** par défaut.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
-   Cette option n'est pas disponible dans l'environnement de développement.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Pour définir cette option du compilateur par programme, consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileOnly%2A>  
  
## Exemple  
 La ligne de commande suivante crée les fichiers objets FIRST.obj et SECOND.obj.  THIRD.obj est ignoré.  
  
```  
CL /c FIRST.C SECOND.C THIRD.OBJ  
```  
  
 Pour créer un fichier exécutable, vous devez appeler LINK :  
  
```  
LINK firsti.obj second.obj third.obj /OUT:filename.exe  
```  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)