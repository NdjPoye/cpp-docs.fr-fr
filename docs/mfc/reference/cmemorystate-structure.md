---
title: "CMemoryState Structure | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMemoryState"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMemoryState structure"
  - "détection des fuites de mémoire"
  - "fuites de mémoire, détecter"
ms.assetid: 229d9de7-a6f3-4cc6-805b-5a9d9b1bfe1d
caps.latest.revision: 19
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMemoryState Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Offre un moyen pratique de détection des fuites de mémoire dans votre programme.  
  
## Syntaxe  
  
```  
struct CMemoryState  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMemoryState::CMemoryState](../Topic/CMemoryState::CMemoryState.md)|Construit une structure classe classe qui contrôle les points de contrôle de mémoire.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMemoryState::Checkpoint](../Topic/CMemoryState::Checkpoint.md)|Obtient un instantané \(point de contrôle\) de l'état actuel de la mémoire.|  
|[CMemoryState::Difference](../Topic/CMemoryState::Difference.md)|Calcule la différence entre deux objets de type `CMemoryState`.|  
|[CMemoryState::DumpAllObjectsSince](../Topic/CMemoryState::DumpAllObjectsSince.md)|Fait un résumé de tous les objets actuellement alloués depuis un point de contrôle précédent.|  
|[CMemoryState::DumpStatistics](../Topic/CMemoryState::DumpStatistics.md)|Compléments d'allocation de mémoire d'impression pour un objet d' `CMemoryState` .|  
  
## Notes  
 `CMemoryState` est une structure et n'a pas de classe de base.  
  
 Une « fuite de mémoire » se produit lorsque la mémoire pour un objet est allouée sur le tas mais pas libérée lorsqu'il n'est plus requis.  De telles fuites de mémoire peuvent éventuellement provoquer des erreurs de mémoire insuffisante.  Il existe plusieurs manières d'allouer et libérer la mémoire dans votre programme :  
  
-   À l'aide de la famille d' `malloc`\/**free** des fonctions de la bibliothèque Runtime.  
  
-   À l'aide de les fonctions de gestion de la mémoire API Windows, **LocalAlloc**\/**LocalFree** et **GlobalAlloc**\/**GlobalFree**.  
  
-   À l'aide de C\+\+ **nouveau** et des opérateurs de **supprimer** .  
  
 L'utilisation de diagnostic de `CMemoryState` uniquement détectent des fuites de mémoire pilotées lorsque la mémoire allouée à l'aide de l'opérateur **nouveau** n'est pas libérée avec **supprimer**.  Les deux autres groupes de fonctions de gestion de la mémoire sont des programmes de non\-C\+\+, et combiner leur avec **nouveau** et **supprimer** dans le même programme n'est pas recommandé.  Une macro en outre, `DEBUG_NEW`, est fournie pour remplacer l'opérateur de **nouveau** lorsque vous avez besoin de trace de fichier et de numéro de ligne des allocations de mémoire.  `DEBUG_NEW` est utilisé lorsque vous utiliseriez normalement l'opérateur de **nouveau** .  
  
 Comme avec d'autres diagnostics, le diagnostic d' `CMemoryState` sont uniquement disponibles dans les versions debug de votre programme.  Une version debug doit avoir une constante de **\_DEBUG** définie.  
  
 Si vous pensez que votre programme comporte une fuite de mémoire, vous pouvez utiliser `Checkpoint`, **Difference**, et les fonctions d' `DumpStatistics` pour connaître la différence entre l'état de la mémoire \(objets alloués\) à deux points individuels dans l'exécution du programme.  Ces informations peuvent être utiles pour déterminer si une fonction nettoie tous les objets qu'il alloue.  
  
 Si seulement savoir où le déséquilibre dans l'allocation et la désallocation se produit ne fournit pas d'informations suffisantes, vous pouvez utiliser la fonction d' `DumpAllObjectsSince` pour faire un dump de tous les objets alloués depuis l'appel précédent à `Checkpoint`.  Ce dump indique l'ordre d'allocation, le fichier source et la ligne où l'objet a été alloué \(si vous utilisez `DEBUG_NEW` pour l'allocation\), et la dérivation de l'objet, son adresse, et sa taille.  `DumpAllObjectsSince` appelle également la fonction d' `Dump` de chaque objet pour fournir des informations sur son état actuel.  
  
 Pour plus d'informations sur l'utilisation `CMemoryState` et d'autres diagnostic, consultez l' [Applications MFC de débogage](../Topic/MFC%20Debugging%20Techniques.md).  
  
> [!NOTE]
>  Les déclarations des objets du type `CMemoryState` et les appels aux fonctions membres doivent être encadrées par des directives d' `#if defined(_DEBUG)/#endif`.  Cela entraîne des diagnostics de la mémoire d'être inclus uniquement dans les générations de débogage de votre programme.  
  
## Hiérarchie d'héritage  
 `CMemoryState`  
  
## Configuration requise  
 **Header:** afx.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)