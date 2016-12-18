---
title: "Modifications apport&#233;es &#224; la fonction d&#39;assistance du chargement diff&#233;r&#233; des DLL depuis Visual&#160;C++&#160;6.0 | Microsoft Docs"
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
helpviewer_keywords: 
  - "__delayLoadHelper2 (fonction)"
  - "chargement différé de DLL, nouveautés"
  - "fonctions d'assistance, nouveautés"
  - "PFromRva (méthode)"
ms.assetid: 99f0be69-105d-49ba-8dd5-3be7939c0c72
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Modifications apport&#233;es &#224; la fonction d&#39;assistance du chargement diff&#233;r&#233; des DLL depuis Visual&#160;C++&#160;6.0
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Si plusieurs versions de Visual C\+\+ sont installées sur votre ordinateur ou si vous avez défini votre propre fonction d'assistance, vous risquez d'être touché par les modifications apportées à la fonction d'assistance du chargement différé des DLL.  Par exemple :  
  
-   **\_\_delayLoadHelper** est maintenant **\_\_delayLoadHelper2**  
  
-   **\_\_pfnDliNotifyHook** est maintenant **\_\_pfnDliNotifyHook2**  
  
-   **\_\_pfnDliFailureHook** est maintenant **\_\_pfnDliFailureHook2**  
  
-   **\_\_FUnloadDelayLoadedDLL** est maintenant **\_\_FUnloadDelayLoadedDLL2**  
  
> [!NOTE]
>  Si vous utilisez la fonction d'assistance par défaut, ces modifications ne vous concernent pas.  Les modalités d'appel de l'éditeur de liens restent inchangées.  
  
## Plusieurs versions de Visual C\+\+  
 Si vous disposez de plusieurs versions de Visual C\+\+ sur votre ordinateur, vérifiez que l'éditeur de liens correspond à delayimp.lib.  En cas de non\-concordance, l'éditeur de liens génère une erreur signalant `___delayLoadHelper2@8` ou `___delayLoadHelper@8` en tant que symbole externe non résolu.  Le premier symbole implique un nouvel éditeur de liens avec une ancienne bibliothèque delayimp.lib, le dernier implique un éditeur de liens ancien avec une nouvelle bibliothèque delayimp.lib.  
  
 Si vous obtenez une erreur d'éditeur de liens non résolue, exécutez [dumpbin \/linkermember](../../build/reference/linkermember.md):1 sur la bibliothèque delayimp.lib susceptible de contenir la fonction d'assistance pour savoir quelle est la fonction d'assistance définie à la place.  La fonction d'assistance peut également être définie dans un fichier objet ; exécutez [dumpbin \/symbols](../../build/reference/symbols.md) et recherchez `delayLoadHelper(2)`.  
  
 Si vous êtes certain de disposer de l'éditeur de liens de Visual C\+\+ 6.0 :  
  
-   Exécutez dumpbin dans le fichier .lib ou .obj de l'assistance de chargement différé pour savoir si elle définit **\_\_delayLoadHelper2**.  Si ce n'est pas le cas, vous constatez une défaillance du lien.  
  
-   Définissez **\_\_delayLoadHelper** dans le fichier .lib ou .obj de l'assistance de chargement différé.  
  
## Fonction d'assistance définie par l'utilisateur  
 Si vous avez défini votre propre fonction d'assistance et que vous utilisez la version actuelle de Visual C\+\+, procédez de la façon suivante :  
  
-   Renommez la fonction d'assistance en **\_\_delayLoadHelper2**.  
  
-   Étant donné que les pointeurs du descripteur de différé \(ImgDelayDescr dans delayimp.h\) ont changé, avec un remplacement des adresses absolues \(VA\) par des adresses relatives \(RVA\) qui permet comme prévu un fonctionnement tant dans les programmes à 32 bits que dans ceux qui sont à 64 bits, vous devez les reconvertir en pointeurs.  Une nouvelle fonction a été introduite : PFromRva, qui se trouve dans delayhlp.cpp.  Vous pouvez appliquer cette fonction à chacun des champs du descripteur pour les reconvertir en pointeurs 32 ou 64 bits.  La fonction d'assistance de chargement différé par défaut reste un bon modèle à utiliser comme exemple.  
  
## Chargement de toutes les importations pour une DLL à chargement différé  
 L'éditeur de liens peut charger toutes les importations à partir d'une DLL à chargement différé.  Pour plus d'informations, consultez [Chargement de toutes les importations pour une DLL à chargement différé](../../build/reference/loading-all-imports-for-a-delay-loaded-dll.md).  
  
## Voir aussi  
 [Understanding the Helper Function](http://msdn.microsoft.com/fr-fr/6279c12c-d908-4967-b0b3-cabfc3e91d3d)