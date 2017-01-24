---
title: "/Od (D&#233;sactiver (D&#233;bogage)) | Microsoft Docs"
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
  - "/od"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Od (option du compilateur C++)"
  - "désactiver (déboguer) (option du compilateur C++)"
  - "désactiver les optimisations"
  - "compilation rapide"
  - "pas d'optimisations"
  - "Od (option du compilateur C++)"
  - "-Od (option du compilateur C++)"
ms.assetid: b1ac31b7-e086-4eeb-be5e-488f7513f5f5
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Od (D&#233;sactiver (D&#233;bogage))
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Désactive toutes les optimisations du programme et accélère la compilation.  
  
## Syntaxe  
  
```  
/Od  
```  
  
## Notes  
 Il s'agit de l'option par défaut.  Dans la mesure où elle supprime tout mouvement de code, l'option **\/Od** simplifie le processus de débogage.  Pour plus d'informations sur les options de compilateur utilisées pour le débogage, consultez [\/Z7, \/Zi, \/ZI \(Format des informations de débogage\)](../../build/reference/z7-zi-zi-debug-information-format.md).  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Optimisation**.  
  
4.  Modifiez la propriété **Optimisation**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>.  
  
## Voir aussi  
 [\/O \(Optimiser le code\), options](../../build/reference/o-options-optimize-code.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)   
 [\/Z7, \/Zi, \/ZI \(Format des informations de débogage\)](../../build/reference/z7-zi-zi-debug-information-format.md)