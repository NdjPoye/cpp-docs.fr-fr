---
title: "/QIfist (Supprimer _ftol) | Microsoft Docs"
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
  - "/qifist"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "QIfist (option du compilateur C++)"
  - "-QIfist (option du compilateur C++)"
  - "/QIfist (option du compilateur C++)"
ms.assetid: 1afd32a5-f658-4b66-85f4-e0ce4cb955bd
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /QIfist (Supprimer _ftol)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Supprime l'appel de la fonction d'assistance `_ftol` quand la conversion d'un type à virgule flottante vers un type intégral est requise.  
  
## Syntaxe  
  
```  
/QIfist  
```  
  
## Notes  
  
> [!NOTE]
>  **\/QIfist** n'est disponible que dans le compilateur ciblant x86 ; cette option du compilateur n'est pas disponible dans les compilateurs ciblant [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] ou ARM.  
  
 Outre la conversion d'un type en virgule flottante vers un type intégral, la fonction `_ftol` assure un mode d'arrondi de l'unité en virgule flottante \(FPU\) à zéro \(troncature\), en positionnant les bits 10 et 11 du mot de commande.  La conversion d'un type en virgule flottante vers un type intégral se produit ainsi comme décrit par la norme C ANSI \(la partie fractionnaire du nombre est supprimée\).  Lors de l'utilisation de **\/QIfist**, cette garantie ne s'applique plus.  Le mode d'arrondi sera l'un des quatre modes documentés dans les manuels de référence d'Intel :  
  
-   Arrondi au plus près \(nombre pair si équidistant\)  
  
-   Arrondi vers infini négatif  
  
-   Arrondi vers infini positif  
  
-   Arrondi à zéro  
  
 Vous pouvez utiliser la fonction runtime C [\_control87, \_controlfp, \_\_control87\_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md) pour modifier le comportement d'arrondi de l'unité en virgule flottante \(FPU\).  Le mode d'arrondi par défaut de la FPU est l'« arrondi au plus près ». L'utilisation de **\/QIfist** peut améliorer les performances de votre application, mais non sans risque.  Vous devez tester complètement les portions de votre code qui sont sensibles aux modes d'arrondi avant de vous fier au code généré à l'aide de **\/QIfist** dans des environnements de production.  
  
 [\/arch \(x86\)](../../build/reference/arch-x86.md) et **\/QIfist** ne peuvent pas être utilisés sur le même module \(compiland\).  
  
> [!NOTE]
>  L'option **\/QIfist** n'est pas activée par défaut, car les bits d'arrondi affectent également l'arrondi d'un nombre en virgule flottante vers un autre format en virgule flottante \(qui est effectué après chaque calcul\), de sorte que lorsque vous définissez les indicateurs de l'arrondi dans le style du langage C \(à zéro\), les calculs en virgule flottante peuvent être différents.  Il convient de ne pas utiliser **\/QIfist** si votre code dépend du comportement attendu qui consiste à tronquer la partie fractionnaire du nombre à virgule flottante.  Si vous avez des doutes, évitez d'utiliser **\/QIfist**.  
  
 **\/QIfist** est déconseillé.  Le compilateur a apporté des améliorations considérables à la vitesse de conversion de int vers float.  Pour plus d'informations, consultez [Deprecated Compiler Options in Visual C\+\+ 2005](http://msdn.microsoft.com/fr-fr/aa59fce3-50b8-4f66-9aeb-ce09a7a84cce).  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Ligne de commande**.  
  
4.  Spécifiez l'option du compilateur dans la zone **Options supplémentaires**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [\/Q \(Opérations de bas niveau\), options](../../build/reference/q-options-low-level-operations.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)