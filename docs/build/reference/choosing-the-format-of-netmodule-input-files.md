---
title: "Choix du format des fichiers d&#39;entr&#233;e .netmodule | Microsoft Docs"
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
ms.assetid: 4653d1bd-300f-4083-86f5-d1a06f44e61c
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Choix du format des fichiers d&#39;entr&#233;e .netmodule
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Un fichier .obj MSIL \(compilé avec [\/clr](../../build/reference/clr-common-language-runtime-compilation.md)\) peut également être utilisé comme un fichier .netmodule.  Les fichiers .obj contiennent des métadonnées et des symboles natifs.  Les fichiers .netmodule contiennent uniquement des métadonnées.  
  
 Vous pouvez passer un fichier .obj MSIL à tout autre compilateur Visual Studio via l'option du compilateur \/addmodule \(mais n'oubliez pas que le fichier .obj devient partie intégrante de l'assembly résultant et doit être expédié avec l'assembly\).  Par exemple, Visual C\# et Visual Basic proposent l'option du compilateur \/addmodule.  
  
> [!NOTE]
>  Dans la plupart des cas, vous devrez passer à l'éditeur de liens le fichier .obj de la compilation qui a créé le fichier .net module.  Une exception à cette règle indique si le .netmodule a été créé avec [\/clr:pure](../../build/reference/clr-common-language-runtime-compilation.md).  Passer un fichier du module de la DLL ou de .netmodule MSIL à l'éditeur de liens peut entraîner l'avertissement LNK1107.  
  
 les fichiers .obj, avec leurs fichiers .h associés, que vous référencez via le \#include dans la source, permettent aux applications C\+\+ de consommer les types natifs dans le module, tandis que dans un fichier .netmodule, seuls les types managés peuvent être utilisés par l'application actuelle C\+\+.  Si vous essayez de passer un fichier .obj à \#using, les informations relatives aux types natifs ne sont pas disponibles ; utilisez plutôt \#include pour inclure le fichier .h du fichier .obj.  
  
 D'autres compilateurs Visual Studio ne peuvent utiliser que des types managés provenant d'un module.  
  
 Utilisez la syntaxe suivante pour déterminer si vous devez utiliser un .netmodule ou un fichier .obj en tant que module inséré dans l'éditeur de liens Visual C\+\+ :  
  
-   Si vous générez avec un compilateur Visual Studio autre que Visual C\+\+, produisez un .netmodule et utilisez le .netmodule comme entrée dans l'éditeur de liens.  
  
-   Si vous utilisez le compilateur Visual C\+\+ pour produire des modules et si les modules doivent être utilisés pour générer un élément autre qu'une bibliothèque, employez les fichiers .obj produits par le compilateur comme entrée de module de l'éditeur de liens ; n'utilisez pas le fichier .netmodule comme entrée.  
  
-   Si vos modules sont utilisés pour générer une bibliothèque native \(et non managée\), utilisez les fichiers .obj comme entrée de module dans l'éditeur de liens et générez un fichier bibliothèque .lib.  
  
-   Si vos modules sont utilisés pour générer une bibliothèque managée et si toutes les entrées de module de l'éditeur de liens sont vérifiables \(produites avec \/clr:safe\), utilisez les fichiers .obj comme entrée de module de l'éditeur de liens et générez un fichier bibliothèque .dll \(assembly\) ou un fichier de bibliothèque .netmodule \(module\).  
  
-   Si les modules sont utilisés pour générer une bibliothèque managée, et si toutes les entrées du module à l'éditeur de liens sont produites avec \/clr:pure ou \/clr:safe, utilisez les fichiers .obj comme entrée de module dans l'éditeur de liens et génèrez un fichier .DLL \(assembly\) ou .netmodule \(module\) si vous ne voulez que exposer des types managés de la bibliothèque.  Si vous souhaitez exposer les types managés de la bibliothèque et si vous désirez également que les applications C\+\+ utilisent les types natifs dans la bibliothèque, votre bibliothèque se composera des fichiers .obj pour les modules de composants de bibliothèques \(vous pouvez également expédier les fichiers .h de chaque module afin qu'ils puissent être référencés avec \#include dans le code source\).  
  
-   Si vos modules sont utilisés pour générer une bibliothèque managée, et si un ou plusieurs modules entrés dans l'éditeur de liens sont produits avec \/clr uniquement, utilisez les fichiers .obj comme entrée de module dans l'éditeur de liens et générez un fichier .dll \(assembly\).  Si vous souhaitez exposer les types managés de la bibliothèque et si vous désirez également que les applications C\+\+ utilisent les types natifs dans la bibliothèque, votre bibliothèque se composera des fichiers .obj pour les modules de composants de bibliothèques \(vous pouvez également expédier les fichiers .h de chaque module afin qu'ils puissent être référencés avec \#include dans le code source\).  
  
## Voir aussi  
 [Fichiers .netmodule en tant qu'entrée de l'Éditeur de liens](../../build/reference/netmodule-files-as-linker-input.md)