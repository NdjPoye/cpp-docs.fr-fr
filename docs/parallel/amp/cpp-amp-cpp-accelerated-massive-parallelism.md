---
title: "C++ AMP (C++ Accelerated Massive Parallelism) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
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
  - "C++ Accelerated Massive Parallelism, mise en route"
  - "C++ AMP (voir C++ Accelerated Massive Parallelism)"
ms.assetid: e27824cb-3167-409b-8c3f-a0e476d8f349
caps.latest.revision: 22
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ AMP (C++ Accelerated Massive Parallelism)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

C\+\+ AMP \(Accelerated Massive Parallelism\) accélère l'exécution de votre code C\+\+ en tirant parti du matériel de données parallèles, plus communément présent en tant qu'unité de traitement graphique \(GPU\) sur une carte graphique distincte.  Le modèle de programmation C\+\+ AMP inclut la prise en charge des tableaux multidimensionnels, de l'indexation, de la migration de mémoire, et de la mosaïque.  Inclut également une bibliothèque de fonctions mathématiques.  Vous pouvez utiliser des extensions de langage C\+\+ AMP pour contrôler la façon dont les données sont déplacées de l'UC au GPU et inversement.  
  
## Rubriques connexes  
  
|Titre|Description|  
|-----------|-----------------|  
|[Présentation de C\+\+ AMP](../../parallel/amp/cpp-amp-overview.md)|Décrit les fonctionnalités clés de C\+\+ AMP et de la bibliothèque mathématique.|  
|[Utilisation de fonctions lambda, d'objets de fonctions et de fonctions restreintes](../../parallel/amp/using-lambdas-function-objects-and-restricted-functions.md)|Décrit comment utiliser des expressions lambda, des objets de fonction et des fonctions restreintes dans les appels à la méthode [parallel\_for\_each](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md).|  
|[Utilisation des mosaïques](../../parallel/amp/using-tiles.md)|Décrit comment utiliser les mosaïques pour accélérer le code C\+\+ AMP.|  
|[Utilisation des objets accelerator et accelerator\_view](../../parallel/amp/using-accelerator-and-accelerator-view-objects.md)|Décrit comment utiliser les accélérateurs pour personnaliser l'exécution de votre code sur le GPU.|  
|[Utilisation de C\+\+ AMP dans les applications Windows Store](../../parallel/amp/using-cpp-amp-in-windows-store-apps.md)|Décrit comment utiliser C\+\+ AMP dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] qui utilisent des types Windows Runtime.|  
|[Graphiques \(C\+\+ AMP\)](../../parallel/amp/graphics-cpp-amp.md)|Décrit comment utiliser la bibliothèque graphique C\+\+ AMP.|  
|[Procédure pas à pas : Multiplication des matrices](../../parallel/amp/walkthrough-matrix-multiplication.md)|Montre la multiplication des matrices à l'aide de code et de disposition en mosaïque C\+\+ AMP.|  
|[Procédure pas\-à\-pas : débogage d’une application C\+\+ AMP](../../parallel/amp/walkthrough-debugging-a-cpp-amp-application.md)|Explique comment créer et déboguer une application qui utilise la réduction parallèle pour résumer un grand tableau d'entiers.|  
  
## Référence  
 [Référence \(C\+\+ AMP\)](../../parallel/amp/reference/reference-cpp-amp.md)  
  
 [tile\_static, mot clé](../../cpp/tile-static-keyword.md)  
  
 [restrict \(C\+\+ AMP\)](../../cpp/restrict-cpp-amp.md)  
  
## Autres ressources  
 [Programmation parallèle sur le blog de code natif](http://go.microsoft.com/fwlink/p/?LinkId=238472)  
  
 [Exemples de projet C\+\+ AMP à télécharger](http://go.microsoft.com/fwlink/p/?LinkId=248508)  
  
 [Analyse de code C\+\+ AMP avec le visualiseur concurrentiel](http://go.microsoft.com/fwlink/?LinkID=253987&clcid=0x409)