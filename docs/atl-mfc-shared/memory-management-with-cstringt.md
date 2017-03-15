---
title: "Memory Management with CStringT | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CStringT"
  - "ATL::CStringT"
  - "ATL.CStringT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFixedStringT class, description of"
  - "CString objects, gestion de la mémoire"
  - "CStringT class, gestion de la mémoire"
  - "IAtlStringMgr class, using"
  - "mémoire (C++), utilisation"
  - "chaînes (C++), custom memory management"
  - "chaînes (C++), gestion de la mémoire"
ms.assetid: 88b8342d-19b5-48c4-9cf6-e4c44cece21e
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Memory Management with CStringT
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe [CStringT](../atl-mfc-shared/reference/cstringt-class.md) est une classe de modèle utilisée pour manipuler des chaînes de longueur variable.  La mémoire pour stocker ces chaînes est allouée et libérée par l'intermédiaire d'un objet de gestionnaire de chaînes, associé à chaque instance d' `CStringT`.  MFC et ATL fournissent les instanciations par défaut d' `CStringT`, d' `CString`appelé, d' `CStringA`, et d' `CStringW`, qui manipulent des chaînes de différents types de caractères.  Ces types de caractères sont de type **TCHAR**, `char`, et `wchar_t`, respectivement.  Ces types de chaînes par défaut utilisent un gestionnaire de chaînes qui alloue la mémoire du tas de processus \(dans ATL\) ou du tas CRT \(dans MFC\).  Pour les applications classiques, ce modèle d'allocation de mémoire est suffisante.  Toutefois, étant donné que le code qui l'utilisation intensive des chaînes \(ou code multithread\) que les gestionnaires par défaut de stockage peuvent ne pas exécuter de façon optimale.  Cette rubrique décrit comment substituer le comportement par défaut de gestion de la mémoire d' `CStringT`, en créant les allocateurs spécifiquement optimisés pour la tâche actuelle.  
  
-   [Implémentation d'un gestionnaire de chaînes personnalisé \(méthode de base\)](../atl-mfc-shared/implementation-of-a-custom-string-manager-basic-method.md)  
  
-   [Manière d'éviter des conflits de tas](../atl-mfc-shared/avoidance-of-heap-contention.md)  
  
-   [Implémentation d'un gestionnaire de chaînes personnalisé \(méthode avancée\)](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md)  
  
-   [CFixedStringT : un exemple d'un gestionnaire de chaînes personnalisé](../atl-mfc-shared/cfixedstringt-example-of-a-custom-string-manager.md)  
  
## Voir aussi  
 [Exemple de CustomString](../top/visual-cpp-samples.md)