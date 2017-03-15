---
title: "/GF (Supprimer les doublons) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.StringPooling"
  - "VC.Project.VCCLWCECompilerTool.StringPooling"
  - "/gf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/GF (option du compilateur C++)"
  - "chaînes dupliquées"
  - "Supprimer les doublons (option du compilateur C++)"
  - "GF (option du compilateur C++)"
  - "-GF (option du compilateur C++)"
  - "regroupement des chaînes (option du compilateur C++)"
  - "chaînes (C++), regroupement"
ms.assetid: bb7b5d1c-8e1f-453b-9298-8fcebf37d16c
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# /GF (Supprimer les doublons)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Permet au compilateur de créer une seule copie des chaînes identiques dans l'image de programme et en mémoire pendant l'exécution.  Il s'agit d'une optimisation appelée *regroupement des chaînes* qui peut créer des programmes plus petits.  
  
## Syntaxe  
  
```  
/GF  
```  
  
## Notes  
 Si vous utilisez l'option **\/GF**, le système d'exploitation n'échange pas la partie chaîne de la mémoire et peut relire les chaînes à partir du fichier image.  
  
 **\/GF** regroupe les chaînes en lecture seule.  Si vous essayez de modifier les chaînes sous **\/GF**, une erreur d'application se produit.  
  
 Le regroupement des chaînes permet de transformer ce qui était censé représenter des pointeurs multiples désignant des mémoires tampons multiples en pointeurs multiples désignant une seule mémoire tampon.  Dans le code suivant, `s` et `t` sont initialisées avec la même chaîne.  Sous l'effet du regroupement des chaînes, elles pointent vers la même mémoire :  
  
```  
char *s = "This is a character buffer";  
char *t = "This is a character buffer";  
```  
  
> [!NOTE]
>  L'option [\/ZI](../../build/reference/z7-zi-zi-debug-information-format.md), utilisée pour Modifier & Continuer, définit automatiquement l'option **\/GF**.  
  
> [!NOTE]
>  L'option du compilateur **\/GF** crée une section adressables pour chaque chaîne unique.  Et par défaut, un fichier objet peut contenir jusqu'à 65 536 sections adressables.  Si votre programme contient plus de 65 536 chaînes, utilisez l'option du compilateur [\/bigobj](../../build/reference/bigobj-increase-number-of-sections-in-dot-obj-file.md) pour créer plus de sections.  
  
 **\/GF** est appliqué lorsque [\/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md) ou **\/O2** est utilisé.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Génération de code**.  
  
4.  Modifiez la propriété **Activation du regroupement des chaînes**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StringPooling%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)