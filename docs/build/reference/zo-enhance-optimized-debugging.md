---
title: "/Zo (Am&#233;liorer le d&#233;bogage optimis&#233;) | Microsoft Docs"
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
  - "-Zo"
  - "/Zo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zo (option du compilateur C++)"
  - "Zo (option du compilateur C++)"
  - "-Zo (option du compilateur C++)"
ms.assetid: eea8d89a-7fe0-4fe1-86b2-7689bbebbd7f
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Zo (Am&#233;liorer le d&#233;bogage optimis&#233;)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Génère des informations de débogage avancées pour le code optimisé dans des builds autres que Debug.  
  
## Syntaxe  
  
```cpp  
/Zo[-]  
```  
  
## Notes  
 Le commutateur du compilateur **\/Zo** génère des informations de débogage avancées pour le code optimisé.  L'optimisation peut utiliser des registres pour les variables locales, réorganiser le code, vectoriser les boucles et placer les appels de fonction inline.  Ces optimisations peuvent rendre moins visible la relation entre le code source et le code objet compilé.  Le commutateur **\/Zo** indique au compilateur de générer des informations de débogage supplémentaires pour les variables locales et les fonctions inline.  Utilisez\-le pour voir les variables dans les fenêtres **Automatique**, **Variables locales** et **Espion** quand vous parcourez pas à pas le code optimisé dans le débogueur de Visual Studio.  Il permet également aux traces de pile d'afficher les fonctions inline dans le débogueur WinDBG.  Les builds Debug pour lesquelles les optimisations sont désactivées \([\/Od](../../build/reference/od-disable-debug.md)\) n'ont pas besoin des informations de débogage supplémentaires générées quand **\/Zo** est spécifié.  Utilisez le commutateur **\/Zo** pour déboguer des configurations Release avec l'optimisation activée.  Pour plus d'informations sur les commutateurs d'optimisation, consultez [\/O \(Optimiser le code\), options](../../build/reference/o-options-optimize-code.md).  L'option **\/Zo** est activée par défaut dans Visual Studio 2015 quand vous spécifiez des informations de débogage avec **\/Zi** ou **\/Z7**.  Spécifiez **\/Zo\-** pour désactiver explicitement cette option du compilateur.  
  
 Le commutateur **\/Zo** est disponible dans Visual Studio 2013 Update 3 et il remplace le commutateur **\/d2Zi\+** qui n'était pas documenté auparavant.  
  
### Pour définir l'option de compilateur \/Zo dans Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriétés** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Sélectionnez le dossier **Propriétés de configuration**, **C\/C\+\+**.  
  
3.  Sélectionnez la page de propriétés **Ligne de commande**.  
  
4.  Modifiez la propriété **Options supplémentaires** pour y inclure `/Zo`, puis choisissez **OK**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [\/O \(Optimiser le code\), options](../../build/reference/o-options-optimize-code.md)   
 [\/Z7, \/Zi, \/ZI \(Format des informations de débogage\)](../../build/reference/z7-zi-zi-debug-information-format.md)   
 [Modifier&Continuer](../Topic/Edit%20and%20Continue.md)