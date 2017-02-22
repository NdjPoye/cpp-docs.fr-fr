---
title: "Dernier caract&#232;re d&#39;une cha&#238;ne | Microsoft Docs"
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
  - "dernier caractère de chaîne"
  - "MBCS (C++), dernier caractère de chaîne"
ms.assetid: 0a180376-4e55-41e8-9c64-539c7b6d8047
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# Dernier caract&#232;re d&#39;une cha&#238;ne
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez les conseils suivants :  
  
-   Dans de nombreux cas, les plages des octets de queue se superposent sur le jeu de caractères ASCII.  Vous pouvez en toute sécurité utiliser des analyses au niveau de l'octet pour les caractères de contrôle \(inférieur à 32\).  
  
-   La ligne de code suivante peut contrôler si le dernier caractère d'une chaîne est une barre oblique inverse :  
  
    ```  
    if ( sz[ strlen( sz ) - 1 ] == '\\' )    // Is last character a '\'?  
        // . . .  
    ```  
  
     Dans la mesure où `strlen` n'est pas compatible MBCS, il retourne le nombre d'octets \(et non le nombre de caractères\) d'une chaîne multioctets.  Il est à noter que dans certaines pages de codes \(932, par exemple\), '\\' \(0x5c\) est un octet de queue valide \(`sz` est une chaîne C\).  
  
     Vous pouvez réécrire le code de la façon suivante :  
  
    ```  
    char *pLast;  
    pLast = _mbsrchr( sz, '\\' );    // find last occurrence of '\' in sz  
    if ( pLast && ( *_mbsinc( pLast ) == '\0' ) )  
        // . . .  
    ```  
  
     Ce code utilise les fonctions MBCS `_mbsrchr` et `_mbsinc`.  Dans la mesure où ces fonctions sont compatibles MBCS, elles peuvent faire la différence entre un caractère « \\ » et un octet de queue « \\ ».  Le code exécute une action si le dernier caractère de la chaîne est null \('\\0'\).  
  
## Voir aussi  
 [Conseils de programmation MBCS](../text/mbcs-programming-tips.md)   
 [Assignation de caractère](../text/character-assignment.md)