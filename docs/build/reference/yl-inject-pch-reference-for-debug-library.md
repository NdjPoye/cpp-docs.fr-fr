---
title: "/Yl (Injecter une r&#233;f&#233;rence PCH pour une biblioth&#232;que de d&#233;bogage) | Microsoft Docs"
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
  - "/yi"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Yl (option du compilateur C++)"
  - "Yl (option du compilateur C++)"
  - "-Yl (option du compilateur C++)"
ms.assetid: 8e4a396a-6790-4a9f-8387-df015a3220e7
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Yl (Injecter une r&#233;f&#233;rence PCH pour une biblioth&#232;que de d&#233;bogage)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisée lors de la création d'une bibliothèque de débogage qui utilise des en\-têtes précompilés et lorsque la génération échoue.  
  
## Syntaxe  
  
```  
/Ylsymbol  
```  
  
```  
/Yl-  
```  
  
## Arguments  
 `symbol`  
 Symbole arbitraire à stocker dans le module objet.  
  
 \-  
 Un signe moins \(\-\) qui désactive explicitement l'option **\/Yl** du compilateur.  
  
## Notes  
 Par défaut, le compilateur utilise l'option **\/Yl** \(sans spécifier un *symbol*\).  L'option de **\/Yl** active le débogueur pour obtenir des informations complètes sur les types.  **\/Yl\-** désactive le comportement par défaut.  
  
 Quand vous compilez un module avec **\/Yc** et **\/Yl**`symbol`, le compilateur crée un symbole se présentant comme \_\_@@\_PchSym\_@00@...@`symbol`, où les points de suspension \(...\) représentent une chaîne de caractères générée par le compilateur, et le stocke dans le module objet.  Tout fichier source que vous compilez avec cet en\-tête précompilé fait référence au symbole spécifié, ce qui amène l'éditeur de liens à incorporer le module objet et ses informations de débogage à partir de la bibliothèque.  
  
 Si vous utilisez cette option, vous risquez de générer l'erreur LNK1211.  Lorsque vous spécifiez les options [\/Yc \(Créer un fichier d'en\-tête précompilé\)](../../build/reference/yc-create-precompiled-header-file.md) et [\/Z7, \/Zi, \/ZI \(Format des informations de débogage\)](../../build/reference/z7-zi-zi-debug-information-format.md), le compilateur crée un fichier d'en\-tête précompilé contenant des informations de débogage.  Une erreur peut se produire quand vous stockez l'en\-tête précompilé dans une bibliothèque, que vous utilisez la bibliothèque pour générer un module objet et que le code source ne fait référence à aucune des fonctions définies dans le fichier d'en\-tête précompilé.  
  
 Pour résoudre le problème, spécifiez **\/Yl**`symbol` \(où `symbol` est le nom d'un symbole arbitraire dans la bibliothèque\) lorsque vous créez un fichier d'en\-tête précompilé qui ne contient aucune définition de fonction.  Cette option indique au compilateur de stocker les informations de débogage dans le fichier d'en\-tête précompilé.  
  
 Pour plus d'informations sur les en\-têtes précompilés, consultez :  
  
-   [\/Y \(En\-têtes précompilés\)](../../build/reference/y-precompiled-headers.md)  
  
-   [Création de fichiers d'en\-tête précompilés](../../build/reference/creating-precompiled-header-files.md)  
  
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