---
title: "/X (Ignorer les chemins d&#39;acc&#232;s Include standard) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/x"
  - "VC.Project.VCCLCompilerTool.IgnoreStandardIncludePath"
  - "VC.Project.VCCLWCECompilerTool.IgnoreStandardIncludePath"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/X (option du compilateur C++)"
  - "Ignorer les chemins d'accès Include standard (option du compilateur)"
  - "répertoires Include, ignorer les chemins d'accès standard"
  - "fichiers Include, ignorer le chemin d'accès standard"
  - "X (option du compilateur)"
  - "-X (option du compilateur C++)"
ms.assetid: 16bdf2cc-c8dc-46e4-bdcc-f3caeba5e1ef
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# /X (Ignorer les chemins d&#39;acc&#232;s Include standard)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Empêche le compilateur de rechercher les fichiers Include dans les répertoires spécifiés dans les variables d'environnement PATH et INCLUDE.  
  
## Syntaxe  
  
```  
/X  
```  
  
## Notes  
 Vous pouvez utiliser cette option avec l'option [\/I \(Autres répertoires Include\)](../../build/reference/i-additional-include-directories.md) \(**\/I**`directory`\).  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Préprocesseur**.  
  
4.  Modifiez la propriété **Chemin d'accès Include standard ignoré**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.IgnoreStandardIncludePath%2A>.  
  
## Exemple  
 Dans la commande suivante, `/X` indique au compilateur d'ignorer les emplacements spécifiés par les variables d'environnement PATH et INCLUDE, et `/I` spécifie le répertoire dans lequel les fichiers Include doivent être recherchés :  
  
```  
CL /X /I \ALT\INCLUDE MAIN.C  
```  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)