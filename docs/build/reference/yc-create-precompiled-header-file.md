---
title: "/Yc (Cr&#233;er un fichier d&#39;en-t&#234;te pr&#233;compil&#233;) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.UsePrecompiledHeader"
  - "/yc"
  - "VC.Project.VCCLWCECompilerTool.PrecompiledHeaderThrough"
  - "VC.Project.VCCLWCECompilerTool.UsePrecompiledHeader"
  - "VC.Project.VCCLCompilerTool.PrecompiledHeaderThrough"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fichiers .pch, créer"
  - "/Yc (option du compilateur C++)"
  - "fichiers PCH, créer"
  - "fichiers d'en-tête précompilés, créer"
  - "Yc (option du compilateur C++)"
  - "-Yc (option du compilateur C++)"
ms.assetid: 47c2e555-b4f5-46e6-906e-ab5cf21f0678
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /Yc (Cr&#233;er un fichier d&#39;en-t&#234;te pr&#233;compil&#233;)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Prescrit au compilateur de créer un fichier d'en\-tête précompilé \(.pch\) qui représente l'état de la compilation à un moment donné.  
  
## Syntaxe  
  
```  
/Yc[filename]  
```  
  
## Arguments  
 `filename`  
 Spécifie un fichier d'en\-tête \(.h\).  Lorsque cet argument est utilisé, le compilateur compile tout le code jusqu'au fichier .h y compris.  
  
## Notes  
 Lorsque **\/Yc** est spécifié sans argument, le compilateur compile tout le code jusqu'à la fin du fichier source de base, ou jusqu'à ce qu'il rencontre [hdrstop](../../preprocessor/hdrstop.md) dans ce fichier de base.  Le fichier .pch résultant a le même nom de base que votre fichier source de base, sauf si vous spécifiez un nom de fichier différent en utilisant le pragma **hdrstop** ou l'option **\/Fp**.  
  
 Le code précompilé est enregistré dans un fichier dont le nom est créé à partir du nom de base du fichier spécifié avec l'option **\/Yc** et dont l'extension est .pch.  Vous pouvez également utiliser l'option [\/Fp \(Nom de fichier .pch\)](../../build/reference/fp-name-dot-pch-file.md) pour spécifier un nom pour le fichier d'en\-tête précompilé.  
  
 Si vous utilisez **\/Yc**`filename`, le compilateur compile tout le code jusqu'au fichier spécifié \(inclus\) pour toute utilisation ultérieure avec l'option **\/Yu**.  
  
 Si les options **\/Yc**`filename` et [\/Yu \(Utiliser un fichier d'en\-tête précompilé\)](../../build/reference/yu-use-precompiled-header-file.md)`filename` se produisent sur la même ligne de commande et font toutes les deux référence à un nom de fichier identique \(ou l'impliquent\), **\/Yc**`filename` prend la priorité.  Cette fonctionnalité simplifie l'écriture de makefiles.  
  
 Pour plus d'informations sur les en\-têtes précompilés, consultez :  
  
-   [\/Y \(En\-têtes précompilés\)](../../build/reference/y-precompiled-headers.md)  
  
-   [Création de fichiers d'en\-tête précompilés](../../build/reference/creating-precompiled-header-files.md)  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Sélectionnez un fichier .cpp.  Le fichier .cpp doit comprendre \(\#include\) le fichier .h qui contient des informations d'en\-tête précompilées.  Le paramètre **\/Yc** du projet peut être substitué au niveau du fichier.  
  
2.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
3.  Cliquez sur le dossier **C\/C\+\+**.  
  
4.  Cliquez sur la page de propriétés **En\-têtes précompilés**.  
  
5.  Modifiez la propriété **Création\/utilisation d'un en\-tête précompilé en spécifiant un nom de fichier** ou la propriété **Création\/utilisation d'un en\-tête précompilé**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderThrough%2A> et <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader%2A>.  
  
## Exemple  
 Examinons le code ci\-dessous.  
  
```  
#include <afxwin.h>   // Include header for class library  
#include "resource.h" // Include resource definitions  
#include "myapp.h"    // Include information specific to this app  
...  
```  
  
 Lorsque ce code est compilé avec la commande `CL /YcMYAPP.H PROG.CPP`, le compilateur enregistre tout le prétraitement pour AFXWIN.h, RESOURCE.h et MYAPP.h dans un fichier d'en\-tête précompilé appelé MYAPP.pch.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)