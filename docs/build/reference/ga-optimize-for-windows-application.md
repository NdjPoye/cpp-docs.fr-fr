---
title: "/GA (Optimiser pour une application Windows) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.OptimizeForWindowsApplication"
  - "/ga"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/GA (option du compilateur C++)"
  - "GA (option du compilateur C++)"
  - "-GA (option du compilateur C++)"
  - "optimiser les options du compilateur pour Windows"
ms.assetid: be97323e-15a0-4836-862c-95980b51926a
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /GA (Optimiser pour une application Windows)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Se traduit par un code plus performant pour l'accès d'un fichier .exe aux variables de stockage local des threads \(TLS\).  
  
## Syntaxe  
  
```  
/GA  
```  
  
## Notes  
 **\/GA** accélère l'accès aux données déclarées avec [\_\_declspec\(thread\)](../../cpp/declspec.md) dans un programme Windows.  Quand cette option est définie, la macro [\_\_tls\_index](http://msdn.microsoft.com/library/windows/desktop/ms686749) a la valeur par défaut 0.  
  
 L'utilisation de **\/GA** pour une DLL peut donner lieu à une génération de code incorrecte.  
  
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