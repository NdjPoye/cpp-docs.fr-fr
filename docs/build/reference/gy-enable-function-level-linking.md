---
title: "/Gy (Activer la liaison au niveau des fonctions) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.EnableFunctionLevelLinking"
  - "/gy"
  - "VC.Project.VCCLWCECompilerTool.EnableFunctionLevelLinking"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Gy (option du compilateur C++)"
  - "COMDAT (fonction)"
  - "activer la liaison au niveau des fonctions (option du compilateur C++)"
  - "Gy (option du compilateur C++)"
  - "-Gy (option du compilateur C++)"
  - "fonctions empaquetées"
ms.assetid: 0d3cf14c-ed7d-4ad3-b4b6-104e56f61046
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# /Gy (Activer la liaison au niveau des fonctions)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Permet au compilateur d'empaqueter des fonctions individuelles sous la forme de fonctions empaquetées \(COMDATs\).  
  
## Syntaxe  
  
```  
/Gy[-]  
```  
  
## Notes  
 L'éditeur de liens requiert que les fonctions soient empaquetées séparément en tant que COMDAT de façon à exclure ou à ordonner des fonctions individuelles dans un fichier .exe ou DLL.  
  
 Vous pouvez utiliser l'option [\/OPT \(Optimisations\)](../../build/reference/opt-optimizations.md) de l'éditeur de liens de façon à exclure des fonctions empaquetées non référencées dans le fichier .exe.  
  
 Vous pouvez utiliser l'option [\/ORDER \(Mettre les fonctions dans l'ordre\)](../../build/reference/order-put-functions-in-order.md) de l'éditeur de liens pour inclure des fonctions empaquetées dans un ordre spécifié dans le fichier .exe.  
  
 Les fonctions inline sont toujours empaquetées si elles sont instanciées en tant qu'appels \(ce qui se produit, par exemple, si la fonctionnalité inline est désactivée ou si vous acceptez une adresse de fonction\).  De plus, les fonctions membres C\+\+ définies dans la déclaration de classes sont empaquetées automatiquement, ce qui n'est pas le cas d'autres fonctions, et la sélection de cette option est requise pour les compiler en tant que fonctions empaquetées.  
  
> [!NOTE]
>  L'option [\/ZI](../../build/reference/z7-zi-zi-debug-information-format.md), utilisée pour Modifier & Continuer, définit automatiquement l'option **\/Gy**.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Génération de code**.  
  
4.  Modifiez la propriété **Activer la liaison au niveau des fonctions**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFunctionLevelLinking%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)