---
title: "/Fx (Fusionner le code inject&#233;) | Microsoft Docs"
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
  - "VC.Project.VCCLWCECompilerTool.ExpandAttributedSource"
  - "/Fx"
  - "VC.Project.VCCLCompilerTool.ExpandAttributedSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Fx (option du compilateur C++)"
  - "-Fx (option du compilateur C++)"
  - "code injecté"
  - "fusionner le code injecté"
  - "/Fx (option du compilateur C++)"
ms.assetid: 14f0e301-3bab-45a3-bbdf-e7ce66f20560
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Fx (Fusionner le code inject&#233;)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Produit une copie de chaque fichier source avec le code injecté fusionné dans la source.  
  
## Syntaxe  
  
```  
/Fx  
```  
  
## Notes  
 Pour distinguer un fichier source fusionné d’un fichier source d’origine, **\/Fx** ajoute une extension .mrg entre le nom de fichier et l’extension de fichier. Par exemple, un fichier nommé MyCode.cpp contenant du code avec attributs et généré avec **\/Fx** crée un fichier nommé MyCode.mrg.cpp contenant le code suivant :  
  
```  
//+++ Start Injected Code [no_injected_text(true)];      // Suppress injected text, it has // already been injected #pragma warning(disable: 4543) // Suppress warnings about skipping // injected text #pragma warning(disable: 4199) // Suppress warnings from attribute // providers //--- End Injected Code  
```  
  
 Dans un fichier .mrg, le code injecté en raison d’un attribut est délimité comme suit :  
  
```  
//+++ Start Injected Code ... //--- End Injected Code  
```  
  
 L’attribut [no\_injected\_text](../../windows/no-injected-text.md) attribut est incorporé dans un fichier .mrg, ce qui permet la compilation du fichier .mrg sans réinjection de texte.  
  
 Notez bien que le fichier source .mrg est destiné à être une représentation sous forme de code source injecté par le compilateur. Le fichier .mrg ne peut pas être compilé ou s’exécuter exactement comme le fichier source d’origine.  
  
 Les macros ne sont pas développées dans le fichier .mrg.  
  
 Si votre programme inclut un fichier d’en\-tête qui utilise du code injecté, **\/Fx** génère un fichier .mrg.h pour cet en\-tête.**\/Fx** ne fusionne pas les fichiers include qui n’utilisent pas de code injecté.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés des **Fichiers de sortie**.  
  
4.  Modifiez la propriété **Développement de la source avec attributs**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ExpandAttributedSource%2A>.  
  
## Voir aussi  
 [Options du fichier de sortie \(\/F\)](../../build/reference/output-file-f-options.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)