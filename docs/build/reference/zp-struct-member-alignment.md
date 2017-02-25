---
title: "/Zp (Alignement des membres de la structure) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/zp"
  - "VC.Project.VCCLCompilerTool.StructMemberAlignment"
  - "VC.Project.VCCLWCECompilerTool.StructMemberAlignment"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zp (option du compilateur C++)"
  - "alignement des membres de la structure (option du compilateur)"
  - "Zp (option du compilateur)"
  - "-Zp (option du compilateur C++)"
ms.assetid: 5242f656-ed9b-48a3-bc73-cfcf3ed2520f
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /Zp (Alignement des membres de la structure)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Contrôle la manière dont les membres d'une structure sont comprimés en mémoire et spécifie la même compression pour toutes les structures contenues dans un module.  
  
## Syntaxe  
  
```  
/Zp[1|2|4|8|16]  
```  
  
## Notes  
 Lorsque vous spécifiez cette option, chaque membre de la structure situé après le premier est stocké soit côté taille du type de membre soit côté limites de `n` octet\(s\) \(où `n` équivaut à 1, 2, 4, 8 ou 16\), selon la valeur la plus petite.  
  
 Les valeurs disponibles sont décrites dans le tableau suivant.  
  
 1  
 Compresse les structures sur des limites d'un \(1\) octet.  Identique à **\/Zp**.  
  
 2  
 Compresse les structures sur des limites de 2 octets.  
  
 4  
 Compresse les structures sur des limites de 4 octets.  
  
 8  
 Compresse les structures sur des limites de 8 octets \(par défaut\).  
  
 16  
 Compresse les structures sur des limites de 16 octets.  
  
 Vous ne devez utiliser cette option que si vous avez des besoins spécifiques en matière d'alignement.  
  
 Vous pouvez également utiliser [pack](../../preprocessor/pack.md) pour déterminer la compression des structures.  Pour plus d'informations sur l'alignement, consultez :  
  
-   [align](../../cpp/align-cpp.md)  
  
-   [\_\_alignof, opérateur](../../cpp/alignof-operator.md)  
  
-   [\_\_unaligned](../../cpp/unaligned.md)  
  
-   [Exemples d'alignement de structure](../../build/examples-of-structure-alignment.md) \(spécifique à x64\)  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Génération de code**.  
  
4.  Modifiez la propriété **Alignement des membres de la structure**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StructMemberAlignment%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)