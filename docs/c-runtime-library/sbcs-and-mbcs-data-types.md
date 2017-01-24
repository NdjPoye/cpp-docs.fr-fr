---
title: "Types de donn&#233;es SBCS et MBCS | Microsoft Docs"
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
  - "MBCS"
  - "SBCS"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "types de données SBCS et MBCS"
  - "types de données [C], MBCS et SBCS"
ms.assetid: 4c3ef9da-e397-48d4-800e-49dba36db171
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Types de donn&#233;es SBCS et MBCS
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Toute routine de bibliothèque Runtime de Microsoft `MBCS` qui gère un seul caractères multioctets ou un octet de caractères multioctets attend un argument `unsigned` `int` \(où 0x00 \<\= valeur de caractère \< \= 0xFFFF \= et \<\= valeur d'octet \<\= 0xFF\).  Une routine `MBCS` qui gère les octets multioctets ou les caractères de chaînes s'attend à ce qu'une chaîne de caractères multi\-octets soit représenté en tant qu'un pointeur `unsigned` `char`.  
  
> [!CAUTION]
>  Chaque octet d'un caractères multioctets peut être représenté dans un `char`de 8 bits.  Cependant, un caractère d'un octet `SBCS` ou `MBCS` de type `char` avec une valeur plus grande que 0x7F est négative.  Lorsque ce caractère est converti directement en `int` ou `long`, le signe du résultat est étendu par le compilateur et peut donc donner des résultats inattendus.  
  
 Par conséquent il est préférable de représenter un octet d'un caractères multioctets comme un `unsigned char`de 8 bits.  Ou, pour éviter un résultat négatif, convertir simplement un caractère codé sur un octet de type `char` en un `unsigned char` avant de le convertir en `int` ou en `long`.  
  
 Dans la mesure où certaines fonctions `SBCS` de gestion des chaînes prennent des arguments \(signés\) `char*` un avertissement du compilateur d'incompatibilité de type se produira quand `_MBCS` sera défini.  Il existe trois manières d'éviter cet avertissement, répertorié dans l'ordre efficacité :  
  
1.  Utilisez des fonctions inlines "type\-safe" dans TCHAR.H.  Il s'agit du comportement par défaut.  
  
2.  Utilisez les macros "directes" dans TCHAR.H en définissant `_MB_MAP_DIRECT` sur la ligne de commande.  Si vous utilisez ces macros, vous devez faire correspondre les types manuellement.  Il s'agit de la méthode la plus sûre, mais elle n'est pas type\-safe.  
  
3.  Utilisez les fonctions de type sécurisé de la fonction de bibliothèque liée statiquement dans Tchar.h.  Pour cela, définissez la constante `_NO_INLINING` sur la ligne de commande.  Il s'agit de la méthode la plus lente, mais la plus type\-safe.  
  
## Voir aussi  
 [Internationalisation](../c-runtime-library/internationalization.md)   
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)