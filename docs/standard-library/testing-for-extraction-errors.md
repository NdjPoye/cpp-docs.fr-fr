---
title: "Tester les erreurs d&#39;extraction | Microsoft Docs"
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
  - "erreurs d'extraction"
ms.assetid: 6a681028-adba-4557-8f7b-f137932905f8
caps.latest.revision: 9
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Tester les erreurs d&#39;extraction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fonctions traitant les erreurs de sorties, décrites dans [Fonctions de traitement d'erreurs](../standard-library/output-file-stream-member-functions.md), s'appliquent aux flux d'entrée.  Le test des erreurs lors de l'extraction est important.  Considérez l'instruction suivante :  
  
```  
cin >> n;  
```  
  
 Si `n` est un entier signé, une valeur supérieure à 32.767 \(la valeur maximale autorisée, ou MAX\_INT\) définit le bit de `fail` du flux de données, et l'objet `cin` devient inutilisable.  Toutes les extractions suivantes provoquent un retour immédiat sans valeur stockée.  
  
## Voir aussi  
 [Flux d'entrée](../standard-library/input-streams.md)