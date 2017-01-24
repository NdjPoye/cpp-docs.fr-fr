---
title: "/Oi (G&#233;n&#233;rer des fonctions intrins&#232;ques) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.EnableIntrinsicFunctions"
  - "/oi"
  - "VC.Project.VCCLWCECompilerTool.EnableIntrinsicFunctions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Oi (option du compilateur C++)"
  - "générer des fonctions intrinsèques (option du compilateur C++)"
  - "fonctions intrinsèques, générer"
  - "Oi (option du compilateur C++)"
  - "-Oi (option du compilateur C++)"
ms.assetid: fa4a3bf6-0ed8-481b-91c0-add7636132b4
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Oi (G&#233;n&#233;rer des fonctions intrins&#232;ques)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Remplace certains appels de fonction par des formes intrinsèques ou d'autres formes spéciales de la fonction permettant à votre application de s'exécuter plus vite.  
  
## Syntaxe  
  
```  
/Oi[-]  
```  
  
## Notes  
 Les programmes qui utilisent des fonctions intrinsèques sont plus rapides, car ils n'ont pas la charge mémoire des appels de fonction, mais peuvent être plus volumineux en raison du code supplémentaire créé.  
  
 Pour plus d'informations sur les fonctions possédant des formes intrinsèques, consultez [intrinsic](../../preprocessor/intrinsic.md).  
  
 **\/Oi** est uniquement une demande au compilateur de remplacer des appels de fonction par des formes intrinsèques ; le compilateur peut appeler la fonction \(sans remplacer l'appel de fonction par une forme intrinsèque\) si cela entraîne de meilleures performances.  
  
 **Section spécifique à x86**  
  
 Les fonctions en virgule flottante intrinsèques n'effectuent pas de vérifications spéciales sur les valeurs d'entrée ; elles travaillent donc dans des plages restreintes d'entrée et se caractérisent par une gestion des exceptions et des conditions de limites différentes de celles des routines des bibliothèques portant le même nom.  L'utilisation de formes intrinsèques véritables implique la perte de la gestion des exceptions IEEE, ainsi que la perte des fonctionnalités `_matherr` et `errno` ; cette dernière signifie la perte de compatibilité ANSI.  Cependant, les formes intrinsèques peuvent accélérer considérablement les programmes à forte intensité de calcul en virgule flottante, et pour de nombreux programmes, les problèmes de compatibilité ne représentent qu'une très faible valeur sur le plan pratique.  
  
 Vous pouvez utiliser l'option du compilateur [Za](../../build/reference/za-ze-disable-language-extensions.md) pour substituer génération d'options à virgule flottante intrinsèques vraies.  Dans ce cas, les fonctions sont générées en tant que routines de bibliothèque qui passent directement des arguments au processeur de calcul en virgule flottante au lieu de leur appliquer une transmission de type push sur la pile du programme.  
  
 **FIN Spécifique x86**  
  
 Vous également utiliser [intrinsic](../../preprocessor/intrinsic.md) pour créer des fonctions intrinsèques ou [function \(fonction\)](../../preprocessor/function-c-cpp.md) pour forcer explicitement un appel de fonction.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Optimisation**.  
  
4.  Modifiez la propriété **Activation des fonctions intrinsèques**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableIntrinsicFunctions%2A>.  
  
## Voir aussi  
 [\/O \(Optimiser le code\), options](../../build/reference/o-options-optimize-code.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)   
 [compilateur, intrinsèques](../../intrinsics/compiler-intrinsics.md)