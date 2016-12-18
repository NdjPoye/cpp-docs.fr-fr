---
title: "Conseils de programmation MBCS | Microsoft Docs"
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
  - "_mbcs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "jeux de caractères (C++), multioctets"
  - "MBCS (C++), programmation"
  - "caractères multioctets (C++)"
  - "programmation (C++), MBCS"
ms.assetid: d8ad36b8-917f-474e-8adb-69462adecd17
caps.latest.revision: 8
caps.handback.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Conseils de programmation MBCS
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans de nouveaux développements, vous devriez utiliser l'encodage de caractères Unicode pour toutes les chaînes que les utilisateurs finaux peuvent potentiellement voir.  MBCS est une technologie héritée qui a été remplacée par Unicode.  Cette section fournit des conseils pour les développeurs qui doivent entretenir des programmes existants qui utilisent MBCS et où il n'est pas pratique de convertir au format Unicode.  Ces conseils s'appliquent aux applications MFC et aux applications écrites sans MFC.  Les rubriques traitées ici sont les suivantes :  
  
-   [Conseil général pour la programmation MBCS](../text/general-mbcs-programming-advice.md)  
  
-   [Incrémentation et décrémentation de pointeurs](../text/incrementing-and-decrementing-pointers.md)  
  
-   [Indices d'octet](../text/byte-indices.md)  
  
-   [Dernier caractère d'une chaîne](../text/last-character-in-a-string.md)  
  
-   [Assignation de caractère](../text/character-assignment.md)  
  
-   [Comparaison de caractères](../text/character-comparison.md)  
  
-   [Dépassement de capacité du tampon](../text/buffer-overflow.md)  
  
## Voir aussi  
 [Prise en charge des jeux de caractères multioctets \(MBCS\)](../text/support-for-multibyte-character-sets-mbcss.md)