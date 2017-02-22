---
title: "Indices d&#39;octets | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "indices d'octets (C++)"
  - "MBCS (C++), indices d'octets"
ms.assetid: f6e7774a-86c6-41c2-89e3-74fd46432e47
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# Indices d&#39;octets
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez les conseils suivants :  
  
-   L'utilisation d'un index au niveau de l'octet dans une chaîne pose les mêmes problèmes que ceux posés par la manipulation de pointeurs.  Prenons l'exemple suivant, qui montre comment analyser une chaîne pour une barre oblique inverse :  
  
    ```  
    while ( rgch[ i ] != '\\' )  
        i++;  
    ```  
  
     Cela peut indexer un octet de queue, et non un octet de tête, et ainsi peut ne pas pointer vers un `character`.  
  
-   Utilisez la fonction [\_mbclen](../c-runtime-library/reference/mbclen-mblen-mblen-l.md) pour résoudre le problème précédent :  
  
    ```  
    while ( rgch[ i ] != '\\' )  
        i += _mbclen ( rgch + i );  
    ```  
  
     Ce code indexe correctement un octet de tête, et donc un `character`.  La fonction `_mbclen` détermine la taille d'un caractère \(un ou deux octets\).  
  
## Voir aussi  
 [Conseils de programmation MBCS](../text/mbcs-programming-tips.md)   
 [Dernier caractère d'une chaîne](../text/last-character-in-a-string.md)