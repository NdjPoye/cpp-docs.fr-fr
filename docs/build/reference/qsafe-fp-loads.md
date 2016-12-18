---
title: "/Qsafe_fp_loads | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 2b2ce52d-ba57-4bd3-a739-47a7f8bfaba9
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Qsafe_fp_loads
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nécessite des instructions de déplacement d'entiers pour les valeurs à virgule flottante et désactive certaines optimisations de charge de virgule flottante.  
  
## Syntaxe  
  
```  
/Qsafe_fp_loads  
```  
  
## Notes  
 **\/Qsafe\_fp\_loads** est uniquement disponible dans les compilateurs qui cible x86 ; n'est pas disponible dans les compilateurs qui cible x64 ou ARM.  
  
 **\/Qsafe\_fp\_loads** force le compilateur a utiliser l'instruction entière de mouvements au lieu de l'instruction à virgule flottante de transfert pour déplacer des données entre la mémoire et les registres MMX.  Cette option désactive également l'optimisation de charge de registre pour les valeurs à virgule flottante qui peuvent être chargées dans les chemins d'accès de contrôle multiples lorsque la valeur peut provoquer une exception lors du chargement—par exemple, la valeur NaN.  
  
 Cette option est substituée par [\/fp:except](../../build/reference/fp-specify-floating-point-behavior.md).  **\/Qsafe\_fp\_loads** spécifie un sous\-ensemble du comportement du compilateur qui est spécifiée par **\/fp:except**.  
  
 **\/Qsafe\_fp\_loads** est incompatible avec [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) et [\/fp:fast](../../build/reference/fp-specify-floating-point-behavior.md).  Pour plus d'informations sur les options du compilateur de virgule flottante, consultez [\/fp \(Spécifier le comportement de virgule flottante\)](../../build/reference/fp-specify-floating-point-behavior.md).  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Sélectionnez le dossier **C\/C\+\+**.  
  
3.  Sélectionnez la page de propriétés **Ligne de commande**.  
  
4.  Spécifiez l'option du compilateur dans la zone **Options supplémentaires**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [\/Q \(Opérations de bas niveau\), options](../../build/reference/q-options-low-level-operations.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)