---
title: "/Z7, /Zi, /ZI (Format des informations de d&#233;bogage) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.DebugInformationFormat"
  - "/zi"
  - "/z7"
  - "VC.Project.VCCLWCECompilerTool.DebugInformationFormat"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "compatible C7, option du compilateur [C++]"
  - "-Zl, option du compilateur [C++]"
  - "format des informations de débogage (paramètre)"
  - "ZI, option du compilateur"
  - "-Zi, option du compilateur [C++]"
  - "/ZI, option du compilateur [C++]"
  - "Z7, option du compilateur [C++]"
  - "débogage [C++], fichiers d’informations de débogage"
  - "Zi, option du compilateur [C++]"
  - "none, option du compilateur [C++]"
  - "/Zi, option du compilateur [C++]"
  - "base de données du programme, option du compilateur [C++]"
  - "informations de débogage symboliques complètes"
  - "/Z7, option du compilateur [C++]"
  - "numéros de ligne uniquement, option du compilateur [C++]"
  - "cl.exe, compilateur, options de débogage"
  - "-Z7, option du compilateur [C++]"
ms.assetid: ce9fa7e1-0c9b-47e3-98ea-26d1a16257c8
caps.latest.revision: 21
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Z7, /Zi, /ZI (Format des informations de d&#233;bogage)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sélectionne le type d'informations de débogage créées pour votre programme et spécifie si ces informations doivent être conservées dans des fichiers objets \(.obj\) ou dans une base de données de programme \(PDB\).  
  
## Syntaxe  
  
```  
/Z{7|i|I}  
```  
  
## Notes  
 Les options sont décrites dans le tableau suivant.  
  
 None  
 Ne génère pas d'informations de débogage, d'où une compilation plus rapide.  
  
 **\/Z7**  
 Produit un fichier .obj contenant des informations de débogage symboliques complètes pour une utilisation avec le débogueur.  Les informations de débogage symboliques comprennent les noms et types des variables, ainsi que les fonctions et les numéros de ligne.  Aucun fichier .pdb n'est produit.  
  
 L'absence de fichier .pdb peut présenter un avantage pour les distributeurs de bibliothèques tierces.  Toutefois, les fichiers .obj pour les en\-têtes précompilés sont nécessaires pendant la phase de chaînage et lors du débogage.  Si les fichiers objets .pch contiennent uniquement des informations de type \(et aucun code\), vous devez également compiler avec [\/Yl \(Injecter une référence PCH pour une bibliothèque de débogage\)](../../build/reference/yl-inject-pch-reference-for-debug-library.md).  
  
 **\/Zi**  
 Produit une base de données de programme \(PDB\) qui contient des informations de type et des informations de débogage symboliques à utiliser avec le débogueur.  Les informations de débogage symboliques comprennent les noms et types des variables, ainsi que les fonctions et les numéros de ligne.  
  
 **\/Zi** n'affecte pas les optimisations.  Toutefois, **\/Zi** implique **\/debug** ; consultez [\/DEBUG \(Générer les informations de débogage\)](../../build/reference/debug-generate-debug-info.md) pour plus d'informations.  
  
 Les informations de type sont placées dans le fichier .pdb, et non dans le fichier .obj.  
  
 Vous pouvez utiliser [\/Gm \(Activer la régénération minimale\)](../../build/reference/gm-enable-minimal-rebuild.md) avec **\/Zi**, alors que **\/Gm** n'est pas disponible lors de la compilation avec **\/Z7**.  
  
 Lors de la compilation avec **\/Zi** et **\/clr**, l'attribut <xref:System.Diagnostics.DebuggableAttribute> n'est pas placé dans les métadonnées de l'assembly ; vous devez le spécifier dans le code source, le cas échéant.  Cet attribut peut affecter les performances d'exécution de l'application.  Pour plus d'informations sur la façon dont l'attribut Debuggable affecte les performances et sur la manière de modifier l'impact sur les performances, consultez [Simplification du débogage d'une image](../Topic/Making%20an%20Image%20Easier%20to%20Debug.md).  
  
 **\/ZI**  
 Produit une base de données de programme, telle que décrite ci\-dessus, dans un format prenant en charge la fonctionnalité Modifier  Continuer.  Pour utiliser le débogage Modifier & Continuer, cette option est obligatoire.  Dans la mesure où la plupart des optimisations sont incompatibles avec la fonctionnalité Modifier & Continuer, l'utilisation de l'option **\/ZI** désactive toutes les instructions `#pragma optimize` dans votre code.  
  
 **\/ZI** force l'utilisation de [\/Gy \(Activer la liaison au niveau des fonctions\)](../../build/reference/gy-enable-function-level-linking.md) et de [\/FC \(Chemin d'accès complet du fichier de code source dans les diagnostics\)](../../build/reference/fc-full-path-of-source-code-file-in-diagnostics.md) dans votre compilation.  
  
 **\/ZI** n'est pas compatible avec [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
> [!NOTE]
>  **\/ZI** n'est disponible que dans le compilateur ciblant x86 ; cette option du compilateur n'est pas disponible dans les compilateurs ciblant les processeurs ARM ou [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)].  
  
 Le compilateur nomme la base de données de programme *project*.pdb.  Si vous compilez un fichier sans projet, le compilateur crée une base de données nommée VC*x*0.pdb., où *x* est la version principale de [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] en cours d'utilisation.  Le compilateur incorpore le nom de la base de données PDB dans chaque fichier .obj créé avec cette option, afin d'indiquer au débogueur l'emplacement des informations sur les symboles et les numéros de ligne.  Lorsque vous utilisez cette option, vos fichiers .obj sont plus compacts puisque les informations de débogage ne sont pas stockées dans ces fichiers, mais dans le fichier .pdb.  
  
 Si vous créez une bibliothèque à partir d'objets compilés avec cette option, le fichier .pdb associé doit être disponible lorsque la bibliothèque est liée à un programme.  Ainsi, si vous distribuez la bibliothèque, vous devez aussi distribuer la base de données PDB.  
  
 Pour créer une bibliothèque contenant des informations de débogage sans utiliser de fichiers .pdb, vous devez sélectionner l'option Compatible C 7.0 \(**\/Z7**\) du compilateur.  Si vous utilisez les options des en\-têtes précompilés, les informations de débogage de l'en\-tête précompilé et du reste du code source sont placées dans la base de données PDB.  L'option **\/Yd** est ignorée lorsque l'option de base de données du programme est spécifiée.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Général**.  
  
4.  Modifiez la propriété **Format des informations de débogage**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DebugInformationFormat%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)