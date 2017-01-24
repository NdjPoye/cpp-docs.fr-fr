---
title: "/Fe (Nom de fichier EXE) | Microsoft Docs"
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
  - "/fe"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Fe (option du compilateur C++)"
  - "fichiers exécutables, renommer"
  - "Fe (option du compilateur C++)"
  - "-Fe (option du compilateur C++)"
  - "renommer un fichier (option du compilateur C++)"
ms.assetid: 49f594fd-5e94-45fe-a1bf-7c9f2abb6437
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Fe (Nom de fichier EXE)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie un nom et un répertoire pour le fichier .exe ou DLL créé par le compilateur.  
  
## Syntaxe  
  
```  
/Fepathname  
```  
  
## Notes  
 Sans cette option, le compilateur donne au fichier un nom par défaut en utilisant le nom de base du premier fichier source ou objet spécifié sur la ligne de commande et l'extension .exe ou .dll.  
  
 Si vous spécifiez [\/c \(Compiler sans liaison\)](../../build/reference/c-compile-without-linking.md) pour compiler sans liaison, **\/Fe** reste sans effet.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Général**.  
  
4.  Modifiez la propriété **Fichier de sortie**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>.  
  
## Exemple  
 La ligne de commande suivante compile tous les fichiers source C et édite leurs liens dans le répertoire actif.  Le fichier exécutable résultant est nommé PROCESS.exe et est créé dans le répertoire C:\\BIN.  
  
```  
CL /FeC:\BIN\PROCESS *.C  
```  
  
## Exemple  
 La ligne de commande suivante crée un fichier exécutable `C:\BIN` avec le même nom de base que le premier fichier source ou objet :  
  
```  
CL /FeC:\BIN\ *.C  
```  
  
## Voir aussi  
 [Options du fichier de sortie \(\/F\)](../../build/reference/output-file-f-options.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)   
 [Spécification du nom de chemin](../../build/reference/specifying-the-pathname.md)