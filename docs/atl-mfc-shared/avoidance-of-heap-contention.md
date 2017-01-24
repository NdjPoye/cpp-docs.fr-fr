---
title: "Avoidance of Heap Contention | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "heap contention"
ms.assetid: 797129d7-5f8c-4b0e-8974-bb93217e9ab5
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Avoidance of Heap Contention
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les gestionnaires de chaînes par défaut fournis par les MFC et ATL sont des wrappers simples sur un tas global.  Le tas global est complètement thread\-safe, ce qui signifie que plusieurs threads peuvent allouer et libérer de la mémoire de celle\-ci simultanément sans endommager le tas.  Pour fournir la sécurité des threads, le tas doit sérialiser l'accès à lui\-même.  Cela est généralement faire avec une section critique ou un dispositif de verrouillage similaire.  Chaque fois que le test de deux threads pour accéder au tas en même temps, un thread est bloqué jusqu'à ce que de l'autre la demande thread soit terminé.  Pour de nombreuses applications, cette situation se produit rarement et l'impact sur les performances du module de verrouillage du tas est négligeable.  Toutefois, pour les applications qui accèdent souvent le tas de conflit de threads de verrouillage du tas peut provoquer l'application d'exécuter plus lentement que s'il était monothread \(même sur les ordinateurs avec plusieurs processeurs\).  
  
 Les applications qui utilisent [CStringT](../atl-mfc-shared/reference/cstringt-class.md) sont particulièrement susceptibles de conflit de tas car les opérations sur les objets d' `CStringT` requièrent souvent une redistribution de la mémoire tampon de chaîne.  
  
 Une façon d'alléger le conflit de tas entre les threads consiste à allouer chaque thread les chaînes d'un privé, tas de thread local.  Comme les chaînes allouées avec l'allocateur d'un thread particulier sont utilisées uniquement dans ce thread, l'allocateur n'a pas besoin d'être thread\-safe.  
  
## Exemple  
 L'exemple suivant affiche une procédure de thread qui alloue son propre tas privé non thread\-safe à utiliser pour les chaînes sur ce thread :  
  
 [!code-cpp[NVC_ATLMFC_Utilities#182](../atl-mfc-shared/codesnippet/CPP/avoidance-of-heap-contention_1.cpp)]  
  
## Commentaires  
 Les threads peuvent exécuter à l'aide de cette même procédure de thread mais étant donné que chaque thread possède son propre tas aucun conflit entre les threads.  En outre, le fait que chaque tas n'est pas thread\-safe donne une augmentation des performances mesurable même si une seule copie du thread s'exécute.  C'est le résultat du tas pas à des opérations verrouillées chères protéger l'accès simultané.  
  
 Pour une procédure plus complexe de thread, il peut être utile de stocker un pointeur vers le gestionnaire de chaînes du thread dans un emplacement de \(TLS\) de stockage local des threads.  Cela permet d'autres fonctions appelées par la procédure de thread pour accéder au gestionnaire de chaînes du thread.  
  
## Voir aussi  
 [Memory Management with CStringT](../atl-mfc-shared/memory-management-with-cstringt.md)