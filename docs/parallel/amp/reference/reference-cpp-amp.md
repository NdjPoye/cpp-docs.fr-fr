---
title: "R&#233;f&#233;rence (C++ AMP) | Microsoft Docs"
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
  - "amp/Concurrency::Reference (C++ AMP)"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++ Accelerated Massive Parallelism, référence"
ms.assetid: 372a8aed-8a53-48c9-996f-9c3cf09c9fa8
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# R&#233;f&#233;rence (C++ AMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Cette section contient des informations de référence pour le runtime C\+\+ AMP \(C\+\+ Accelerated Massive Parallelism\).  
  
> [!NOTE]
>  La norme du langage C\+\+ réserve l'utilisation des identificateurs qui commencent par un trait de soulignement \(`_`\) aux implémentations telles que les bibliothèques.  N'utilisez pas de noms commençant par un trait de soulignement dans votre code.  Le comportement des éléments de code dont les noms suivent cette convention n'est pas garanti et est sujet à modification dans les versions ultérieures.  Pour ces raisons, de tels éléments de code sont omis de cette documentation.  
  
## Dans cette section  
 [Concurrency, espace de noms \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)  
 Fournit des classes et des fonctions qui permettent l'accélération de l'exécution du code C\+\+ sur le matériel en parallèle de données.  
  
 [Concurrency::direct3d, espace de noms](../../../parallel/amp/reference/concurrency-direct3d-namespace.md)  
 Fournit les fonctions qui prennent en charge l'interopérabilité D3D  Active de façon transparente les ressources D3D pour le calcul dans le code AMP et les ressources créées dans AMP dans le code D3D, sans créer de copies intermédiaires redondantes.  Vous pouvez utiliser C\+\+ AMP pour accélérer les sections intensives de calcul de façon incrémentielle de vos applications DirectX et utiliser l'API D3D sur les données générées par des calculs AMP.  
  
 [Concurrency::fast\_math, espace de noms](../../../parallel/amp/reference/concurrency-fast-math-namespace.md)  
 Les fonctions dans l'espace de noms `fast_math` ne sont pas conformes C99.  Seuls les versions en simple précision de chaque fonction sont fournies.  Ces fonctions utilisent des fonctions intrinsèques DirectX, qui sont plus rapides que les fonctions correspondantes dans l'espace de noms `precise_math` et ne nécessitent pas de prise en charge en double précision étendue sur l'accélérateur, mais elles sont moins précises.  Il existe deux versions de chaque fonction pour la compatibilité au niveau de la source avec le code C99 ; les deux versions prennent et retournent des valeurs de simple précision.  
  
 [Concurrency::graphics, espace de noms](../../../parallel/amp/reference/concurrency-graphics-namespace.md)  
 Fournit des types et des fonctions conçus pour la programmation graphique.  
  
 [Concurrency::precise\_math, espace de noms](../../../parallel/amp/reference/concurrency-precise-math-namespace.md)  
 Les fonctions dans l'espace de noms `precise_math` sont conformes C99.  La simple précision et les versions à double précision de chaque fonction sont incluses.  Ces fonctions, y compris les fonctions en simple précision, requièrent la prise en charge en double précision étendu sur l'accélérateur.  
  
## Rubriques connexes  
 [C\+\+ AMP \(C\+\+ Accelerated Massive Parallelism\)](../../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)  
 C\+\+ AMP accélère l'exécution de votre code C\+\+ en tirant parti du matériel de données parallèles, plus communément présent en tant qu'unité de traitement graphique \(GPU\) sur une carte graphique distincte.