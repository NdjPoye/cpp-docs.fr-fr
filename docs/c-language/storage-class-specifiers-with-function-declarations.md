---
title: "Sp&#233;cificateurs de classe de stockage avec d&#233;clarations de fonction | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "déclarer des fonctions, spécificateurs"
  - "déclarations externes"
  - "liaison externe, déclarations de fonctions"
  - "liaison externe, spécificateurs de classe de stockage"
  - "spécificateurs de fonction, classe de stockage"
  - "spécificateurs, function (fonction)"
ms.assetid: 801d7df2-efa9-4924-a725-274a5654cfd4
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Sp&#233;cificateurs de classe de stockage avec d&#233;clarations de fonction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser le spécificateur de classe de stockage **static** ou `extern` dans les déclarations de fonctions.  Les fonctions ont toujours des durées de vie globales.  
  
 **Section spécifique à Microsoft**  
  
 Les déclarations de fonctions au niveau interne ont la même signification que les déclarations de fonctions au niveau externe.  Cela signifie qu'une fonction est visible de son point de déclaration jusqu'au reste de l'unité de traduction, même si elle est déclarée au niveau de la portée locale.  
  
 **FIN de la section spécifique à Microsoft**  
  
 Les règles de visibilité des fonctions varient légèrement des règles pour les variables, comme suit :  
  
-   Une fonction déclarée comme étant **static** est visible uniquement dans le fichier source dans lequel elle est définie.  Les fonctions du même fichier source peuvent appeler la fonction **static**, mais les fonctions dans d'autres fichiers sources ne peuvent pas y accéder directement par nom.  Vous pouvez déclarer une autre fonction **static** avec le même nom dans un fichier source différent sans conflit.  
  
-   Les fonctions déclarées comme `extern` sont visibles dans tous les fichiers sources du programme \(sauf si vous redéclarer ultérieurement une fonction comme étant **static**\).  Toute fonction peut appeler une fonction `extern`.  
  
-   Les déclarations de fonctions qui omettent le spécificateur de classe de stockage sont `extern` par défaut.  
  
 **Section spécifique à Microsoft**  
  
 Microsoft permet la redéfinition d'un identificateur `extern` comme étant **static**.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Classes de stockage C](../c-language/c-storage-classes.md)