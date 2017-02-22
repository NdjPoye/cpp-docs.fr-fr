---
title: "/LTCG (G&#233;n&#233;ration de code durant l&#39;&#233;dition de liens) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.LinkTimeCodeGeneration"
  - "VC.Project.VCConfiguration.WholeProgramOptimization"
  - "VC.Project.VCCLWCECompilerTool.WholeProgramOptimization"
  - "/ltcg"
  - "VC.Project.VCCLCompilerTool.WholeProgramOptimization"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LTCG (option de l'éditeur de liens)"
  - "génération de code durant l'édition de liens C++"
  - "LTCG (option de l'éditeur de liens)"
  - "-LTCG (option de l'éditeur de liens)"
ms.assetid: 788c6f52-fdb8-40c2-90af-4026ea2cf2e2
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# /LTCG (G&#233;n&#233;ration de code durant l&#39;&#233;dition de liens)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/LTCG[:INCREMENTAL|:NOSTATUS|:STATUS|:OFF|:PGINSTRUMENT|:PGOPTIMIZE|:PGUPDATE]  
```  
  
## Notes  
 :INCREMENTAL \(facultatif\)  
 Spécifie que l’éditeur de liens applique uniquement une optimisation de l’ensemble du programme ou la génération de code durant l’édition de liens \(LTCG\) à l’ensemble des fichiers affectés par une modification, au lieu de le faire à l’ensemble du projet. Par défaut, cet indicateur n’est pas défini quand \/LTCG est spécifié, et l’ensemble du projet est lié en utilisant l’optimisation de l’ensemble du programme.  
  
 :NOSTATUS &#124; :STATUS \(facultatif\)  
 Spécifie si l’éditeur de liens affiche un indicateur de progression qui indique le pourcentage des liaisons effectué. Par défaut, ces informations d’état ne sont pas affichées.  
  
 :OFF \(facultatif\)  
 Désactive la génération de code durant l’édition de liens. Ce comportement est le même que quand \/LTCG n’est pas spécifié sur la ligne de commande.  
  
 :PGINSTRUMENT \(facultatif\)  
 Cette option est déconseillée. Utilisez à la place **\/LTCG** et **\/GENPROFILE** ou **\/FASTGENPROFILE** pour générer une version instrumentée de l’optimisation guidée par profil.  
  
 Les données recueillies à partir des séries de tests instrumentées sont utilisées pour créer une image optimisée. Pour plus d’informations, consultez [Optimisation guidée par profil](../../build/reference/profile-guided-optimizations.md). La forme abrégée de cette option est \/LTCG:PGI.  
  
 :PGOPTIMIZE \(facultatif\)  
 Cette option est déconseillée. Utilisez à la place **\/LTCG** et **\/USEPROFILE** pour générer une image optimisée. Pour plus d’informations, consultez [Optimisation guidée par profil](../../build/reference/profile-guided-optimizations.md). La forme abrégée de cette option est \/LTCG:PGO.  
  
 :PGUPDATE \(facultatif\)  
 Cette option est déconseillée. Utilisez à la place **\/LTCG** et **\/USEPROFILE** pour générer une image optimisée. Pour plus d’informations, consultez [Optimisation guidée par profil](../../build/reference/profile-guided-optimizations.md). La forme abrégée de cette option est \/LTCG:PGU.  
  
 L’option \/LTCG indique à l’éditeur de liens d’appeler le compilateur et effectuer l’optimisation de la totalité du programme. Vous pouvez également effectuer l’optimisation guidée par profil. Pour plus d’informations, consultez [Optimisation guidée par profil](../../build/reference/profile-guided-optimizations.md).  
  
 Avec les exceptions suivantes, vous ne pouvez pas ajouter des options de l’éditeur de liens à la combinaison de \/LTCG et de \/USEPROFILE de l’optimisation guidée par profil qui n’ont pas été spécifiées dans la combinaison des options \/LTCG et \/GENPROFILE de l’initialisation de l’optimisation guidée par profil précédente :  
  
-   [\/BASE](../../build/reference/base-base-address.md)  
  
-   [\/FIXED](../../build/reference/fixed-fixed-base-address.md)  
  
-   \/LTCG  
  
-   [\/MAP](../../build/reference/map-generate-mapfile.md)  
  
-   [\/MAPINFO](../../build/reference/mapinfo-include-information-in-mapfile.md)  
  
-   [\/NOLOGO](../../build/reference/nologo-suppress-startup-banner-linker.md)  
  
-   [\/OUT](../../build/reference/out-output-file-name.md)  
  
-   [\/PGD](../../build/reference/pgd-specify-database-for-profile-guided-optimizations.md)  
  
-   [\/PDB](../../build/reference/pdb-use-program-database.md)  
  
-   [\/PDBSTRIPPED](../../build/reference/pdbstripped-strip-private-symbols.md)  
  
-   [\/STUB](../../build/reference/stub-ms-dos-stub-file-name.md)  
  
-   [\/VERBOSE](../../build/reference/verbose-print-progress-messages.md)  
  
 Toutes les options de l’éditeur qui sont spécifiées en même temps que les options \/LTCG et \/GENPROFILE pour initialiser l’optimisation guidée par profil n’ont pas besoin d’être spécifiées quand vous générez en utilisant \/LTCG et \/USEPROFILE ; elles sont implicites.  
  
 Le reste de cette rubrique explique \/LTCG relativement à la génération de code durant l’édition de liens.  
  
 \/LTCG est implicite avec [\/GL](../../build/reference/gl-whole-program-optimization.md).  
  
 L’éditeur de liens appelle la génération du code au moment de l’édition de liens si un module lui est passé qui a été compilé à l’aide de **\/GL** ou s’il s’agit d’un module MSIL \(consultez [Fichiers .netmodule en tant qu'entrée de l'Éditeur de liens](../../build/reference/netmodule-files-as-linker-input.md)\). Si vous ne spécifiez pas explicitement **\/LTCG** quand vous passez **\/GL** ou des modules MSIL à l’éditeur de liens, ce dernier le détecte et redémarre la liaison en utilisant **\/LTCG**. Spécifiez explicitement **\/LTCG** quand vous passez **\/GL** et des modules MSIL à l’éditeur de liens pour accélérer au maximum la génération.  
  
 Pour encore améliorer les performances, utilisez **\/LTCG:INCREMENTAL**. Cette option indique à l’éditeur de liens d’optimiser uniquement le jeu de fichiers qui est affecté par la modification d’un fichier source, au lieu de l’ensemble du projet. Ceci peut réduire considérablement le temps nécessaire à l’édition des liens. Il ne s’agit pas de la même option que la liaison incrémentielle.  
  
 **\/LTCG** n’est pas valide pour une utilisation avec [\/INCREMENTAL](../../build/reference/incremental-link-incrementally.md).  
  
Quand **\/LTCG** est utilisé pour lier des modules compilés avec [\/Og](../../build/reference/og-global-optimizations.md), [\/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md), [\/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md) ou [\/Ox](../../build/reference/ox-full-optimization.md), les optimisations suivantes sont effectuées :  
  
-   Expansion inline entre modules  
  
-   Allocation de registre interprocédurale \(seulement sur les systèmes d’exploitation 64 bits\)  
  
-   Convention d’appel personnalisée \(x86 uniquement\)  
  
-   Déplacement TLS réduit \(x86 uniquement\)  
  
-   Alignement de pile double \(x86 uniquement\)  
  
-   Levée d’ambiguïté améliorée de la mémoire \(meilleures informations d’interférence pour les variables globales et les paramètres d’entrée\)  
  
> [!NOTE]
> L’éditeur de liens détermine les optimisations qui ont été utilisées pour compiler chaque fonction et applique les mêmes optimisations au moment de la liaison.  
  
L’utilisation de **\/LTCG** et de **\/Ogt** provoque une optimisation à double alignement.  
  
Si **\/LTCG** et **\/Ogs** sont spécifiés, le double alignement n’est pas effectué. Si la plupart des fonctions d’une application sont compilées pour la rapidité, avec quelques fonctions compilées pour la taille \(par exemple avec le pragma [optimize](../../preprocessor/optimize.md)\), le compilateur effectue un alignement double des fonctions optimisées pour la taille si celles\-ci appellent des fonctions qui requièrent le double alignement.  
  
Si le compilateur peut identifier tous les sites d’appel d’une fonction, le compilateur ignore les modificateurs de convention d’appel explicites sur une fonction et tente d’optimiser la convention d’appel de la fonction :  
  
-   passer des paramètres dans les registres  
  
-   réorganiser les paramètres pour l’alignement  
  
-   supprimer les paramètres inutilisés  
  
Si une fonction est appelée via un pointeur de fonction ou si une fonction est appelée en dehors d’un module qui est compilé avec **\/GL**, le compilateur n’essaie pas d’optimiser la convention d’appel de la fonction.  
  
> [!NOTE]
> Si vous utilisez **\/LTCG** et que vous redéfinissez mainCRTStartup, votre application peut avoir un comportement imprévisible quant au code utilisateur qui s’exécute avant l’initialisation des objets globaux.  Il existe trois façons de régler ce problème : ne pas redéfinir mainCRTStartup, ne pas compiler le fichier qui contient mainCRTStartup en utilisant **\/LTCG** ou initialiser les variables globales et les objets globaux de manière statique.  
  
## \/LTCG et les modules MSIL  
Les modules compilés avec [\/GL](../../build/reference/gl-whole-program-optimization.md) et [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) peuvent être utilisés comme entrée dans l'éditeur de liens si **\/LTCG** est spécifié.  
  
-   **\/LTCG** peut accepter des fichiers objets natifs, des fichiers objets mixtes natifs\/managés \(compilés avec **\/clr**\), des fichiers objets purs \(compilés avec **\/clr:pure**\) et des fichiers objets sécurisés \(compilés avec **\/clr:safe**\).  
  
-   **\/LTCG** accepte les modules .netmodules sécurisés, qui peuvent être créés avec **\/clr:safe \/LN** en Visual C\+\+ et avec **\/target:module** dans les autres compilateurs Visual Studio. Les modules .netmodules créés avec **\/clr** ou **\/clr:pure** ne sont pas acceptés par **\/LTCG**.  
  
-   \/LTCG:PGI n'accepte pas les modules natifs compilés avec **\/GL** et **\/clr**, ou les modules purs \(créés avec **\/clr:pure**\)  
  
#### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriétés** du projet. Consultez [Utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Sélectionnez le dossier **Propriétés de configuration**.  
  
3.  Sélectionnez la page de propriétés **Général**.  
  
4.  Modifiez la propriété **Optimisation de l’ensemble du programme**.  
  
Vous pouvez également appliquer **\/LTCG** à des builds spécifiques en choisissant **Générer**, **Optimisation guidée par profil** dans la barre de menus, ou en choisissant l'une des options d'optimisation guidée par profil dans le menu contextuel du projet.  
  
#### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LinkTimeCodeGeneration%2A>.  
  
## Voir aussi  
[Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)  
[Options de l'Éditeur de liens](../../build/reference/linker-options.md)