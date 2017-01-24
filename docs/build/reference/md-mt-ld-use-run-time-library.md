---
title: "/MD, /MT, /LD (Utiliser la biblioth&#232;que Runtime) | Microsoft Docs"
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
  - "/ld"
  - "/mt"
  - "VC.Project.VCCLWCECompilerTool.RuntimeLibrary"
  - "VC.Project.VCCLCompilerTool.RuntimeLibrary"
  - "/md"
  - "/ml"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LD (option du compilateur C++)"
  - "/MD (option du compilateur C++)"
  - "/MDd (option du compilateur C++)"
  - "/MT (option du compilateur C++)"
  - "/MTd (option du compilateur C++)"
  - "_STATIC_CPPLIB (symbole)"
  - "DLL (C++), options du compilateur"
  - "LD (option du compilateur C++)"
  - "-LD (option du compilateur C++)"
  - "LIBC.lib"
  - "LIBCD.lib"
  - "LIBCMT.lib"
  - "LIBCMTD.lib"
  - "MD (option du compilateur C++)"
  - "-MD (option du compilateur C++)"
  - "MDd (option du compilateur C++)"
  - "-MDd (option du compilateur C++)"
  - "MSVCRT.lib"
  - "MSVCRTD.lib"
  - "MT (option du compilateur C++)"
  - "-MT (option du compilateur C++)"
  - "MTd (option du compilateur C++)"
  - "-MTd (option du compilateur C++)"
  - "multithread (option du compilateur)"
  - "threads (C++), multithread (option du compilateur)"
ms.assetid: cf7ed652-dc3a-49b3-aab9-ad60e5395579
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /MD, /MT, /LD (Utiliser la biblioth&#232;que Runtime)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Indique si un module multithread est une DLL et spécifie les versions retail ou debug de la bibliothèque Runtime.  
  
## Syntaxe  
  
```  
/MD[d]  
/MT[d]  
/LD[d]  
```  
  
## Notes  
  
|Option|Description|  
|------------|-----------------|  
|**\/MD**|Indique à l'application d'utiliser la version multithread spécifique à la DLL de la bibliothèque Runtime.  Définit `_MT` et `_DLL`, puis indique au compilateur de placer le nom de la bibliothèque MSVCRT.lib dans le fichier .obj.<br /><br /> Les applications compilées avec cette option sont liées de manière statique à MSVCRT.lib.  Cette bibliothèque fournit une couche de code qui permet à l'éditeur de liens de résoudre des références externes.  Le code de travail effectif est contenu dans MSVCR*versionnumber*.DLL, qui doit être disponible au moment de l'exécution pour les applications liées avec MSVCRT.lib.|  
|**\/MDd**|Définit `_DEBUG`, `_MT` et `_DLL`, puis indique à l'application d'utiliser la version debug multithread spécifique à la DLL de la bibliothèque Runtime.  Le compilateur place également le nom de la bibliothèque MSVCRTD.lib dans le fichier .obj.|  
|**\/MT**|Indique à l'application d'utiliser la version statique multithread de la bibliothèque Runtime.  Définit `_MT` et indique au compilateur de placer le nom de la bibliothèque LIBCMT.lib dans le fichier .obj de façon à ce que l'éditeur de liens utilise LIBCMT.lib pour résoudre les symboles externes.|  
|**\/MTd**|Définit `_DEBUG` et `_MT`.  Cette option indique également au compilateur d'ajouter le nom de bibliothèque LIBCMTD.lib dans le fichier .obj afin que l'Éditeur de liens utilise LIBCMTD.lib pour résoudre les symboles externes.|  
|**\/LD**|Crée une DLL.<br /><br /> Passe l'option **\/DLL** à l'éditeur de liens.  L'éditeur de liens recherche, mais n'exige pas, une fonction `DllMain`.  Si vous n'écrivez pas de fonction `DllMain`, l'éditeur de liens insère une fonction `DllMain` qui retourne TRUE.<br /><br /> Lie le code de démarrage de la DLL.<br /><br /> Crée une bibliothèque d'importation \(.lib\), si aucun fichier d'exportation \(.exp\) n'est spécifié sur la ligne de commande.  Vous liez la bibliothèque d'importation aux applications qui appellent votre DLL.<br /><br /> Interprète [\/Fe \(Nom de fichier EXE\)](../../build/reference/fe-name-exe-file.md) de manière à nommer une DLL plutôt qu'un fichier .exe.  Par défaut, le nom du programme devient *basename*.dll au lieu de *basename*.exe.<br /><br /> Implique **\/MT** à moins que vous ne spécifiiez explicitement **\/MD**.|  
|**\/LDd**|Crée une DLL de débogage.  Définit `_MT` et `_DEBUG`.|  
  
 Pour plus d'informations sur les bibliothèques Runtime C et les bibliothèques utilisées lors de la compilation avec [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md), consultez [Fonctions de bibliothèque CRT](../../c-runtime-library/crt-library-features.md).  
  
 Tous les modules passés à un appel donné de l'éditeur de liens doivent être compilés avec la même option de compilateur de la bibliothèque Runtime \(**\/MD**, **\/MT**, **\/LD**\).  
  
 Pour plus d'informations sur l'utilisation des versions Debug des bibliothèques Runtime, consultez [Référence sur les bibliothèques Runtime C](../../c-runtime-library/c-run-time-library-reference.md).  
  
 L'article de la Base de connaissances Q140584 indique également comment choisir la bibliothèque Runtime C appropriée.  
  
 Pour plus d'informations sur les DLL, consultez [DLL en Visual C\+\+](../../build/dlls-in-visual-cpp.md).  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Développez le dossier **C\/C\+\+**.  
  
3.  Sélectionnez la page de propriétés **Génération de code**.  
  
4.  Modifiez la propriété **Bibliothèque Runtime**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.RuntimeLibrary%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)