---
title: "/arch (x86) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 9dd5a75d-06e4-4674-aade-33228486078d
caps.latest.revision: 33
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 33
---
# /arch (x86)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie l'architecture pour la génération de code sur x86.  Consultez également [\/arch \(x64\)](../../build/reference/arch-x64.md) et [\/arch \(ARM\)](../../build/reference/arch-arm.md).  
  
## Syntaxe  
  
```  
/arch:[IA32|SSE|SSE2|AVX|AVX2]  
```  
  
## Arguments  
 **\/arch:IA32**  
 Ne spécifie aucune instruction améliorée et spécifie x87 pour les calculs à virgule flottante.  
  
 **\/arch:SSE**  
 Permet l'utilisation d'instructions SSE.  
  
 **\/arch:SSE2**  
 Permet l'utilisation d'instructions SSE2.  Il s'agit de l'instruction par défaut sur les plateformes x86 si aucune option **\/arch** n'est spécifiée.  
  
 **\/arch:AVX**  
 Active l'utilisation des instructions Intel Advanced Vector Extensions.  
  
 **\/arch:AVX2**  
 Active l'utilisation des instructions Intel Advanced Vector Extensions 2.  
  
## Notes  
 Les instructions SSE et SSE2 existent sur divers processeurs Intel et AMD.  Les instructions AVX existe sur les processeurs Intel Sandy Bridge et les processeurs AMD Bulldozer.  Les instructions AVX2 sont prises en charge par les processeurs Intel Haswell et Broadwell et les processeurs basés sur AMD Excavator.  
  
 Les macros `_M_IX86_FP`, `__AVX__` et `__AVX2__` indiquent quelle option de compilateur **\/arch** a été utilisée, le cas échéant.  Pour plus d'informations, consultez [Macros prédéfinies](../../preprocessor/predefined-macros.md).  L'option **\/arch:AVX2** et la macro `__AVX2__` ont été introduites pour la première fois dans Visual Studio 2013 Update 2, version 12.0.34567.1.  
  
 L'optimiseur choisit quand et comment utiliser les instructions SSE et SSE2 quand **\/arch** est spécifié.  Il utilise les instructions SSE et SSE2 pour certains calculs scalaires à virgule flottante quand il détermine qu'il est plus rapide d'utiliser les instructions et les registres SSE\/SSE2 que la pile de registres à virgule flottante x87.  En conséquence, votre code peut en fait utiliser un mélange x87 et SSE\/SSE2 pour les calculs à virgule flottante.  En outre, avec **\/arch:SSE2**, il est possible d'utiliser les instructions SSE2 pour certaines opérations d'entiers 64 bits.  
  
 Outre l'utilisation des instructions SSE et SSE2, le compilateur utilise également d'autres instructions présentes sur les révisions de processeur qui prennent en charge SSE et SSE2.  Un exemple de cela est l'instruction CMOV qui est apparue pour la première fois sur la révision Pentium Pro des processeurs Intel.  
  
 Comme le compilateur x86 génère du code qui utilise par défaut les instructions SSE2, vous devez spécifier **\/arch:IA32** pour désactiver la génération d'instructions SSE et SSE2 pour les processeurs x86.  
  
 **\/arch** affecte uniquement la génération de code pour les fonctions natives.  Lorsque vous utilisez [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) pour compiler, **\/arch** n'a aucun effet sur la génération de code pour les fonctions managées.  
  
 **\/arch** et [\/QIfist](../../build/reference/qifist-suppress-ftol.md) ne sont pas utilisables sur le même compiland.  En particulier, si vous n'utilisez pas `_controlfp` pour modifier le mot de commande FP, le code de démarrage runtime définit le champ de contrôle de précision de mot de commande FPU x87 sur 53 bits.  Par conséquent, chaque opération float ou double d'une expression utilise une mantisse de 53 bits et un exposant de 15 bits.  Toutefois, chaque opération simple précision SSE utilise une mantisse de 24 bits et un exposant de 8 bits, tandis que les opérations double précision SSE2 utilisent une mantisse de 53 bits et un exposant de 11 bits.  Pour plus d'informations, consultez [\_control87, \_controlfp, \_\_control87\_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md).  Ces différences sont possibles dans une même arborescence d'expression, mais pas dans les cas où une affectation d'utilisateurs intervient après chaque sous\-expression.  Considérez ce qui suit :  
  
```c  
  
r = f1 * f2 + d;  // Different results are possible on SSE/SSE2.  
```  
  
 Par rapport à :  
  
```c  
  
t = f1 * f2;   // Do f1 * f2, round to the type of t.  
r = t + d;     // This should produce the same overall result   
               // whether x87 stack is used or SSE/SSE2 is used.  
```  
  
### Pour définir cette option de compilateur pour AVX, AVX2, IA32, SSE ou SSE2 dans Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriétés** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Sélectionnez le dossier **Propriétés de configuration**, **C\/C\+\+**.  
  
3.  Sélectionnez la page de propriétés **Génération de code**.  
  
4.  Modifiez la propriété **Activation du jeu d'instructions amélioré**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>.  
  
## Voir aussi  
 [\/arch \(Architecture d'UC minimale\)](../../build/reference/arch-minimum-cpu-architecture.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)