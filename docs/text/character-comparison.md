---
title: "Comparaison de caract&#232;res | Microsoft Docs"
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
  - "caractères (C++), comparer"
  - "comparer des caractères"
  - "MBCS (C++), comparaison de caractères"
ms.assetid: 18846e44-3e6e-40c4-9b42-3153fb15db20
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 8
---
# Comparaison de caract&#232;res
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez les conseils suivants :  
  
-   La comparaison d'un octet de tête valide et d'un caractère ASCII fonctionne correctement :  
  
    ```  
    if( *sz1 == 'A' )  
    ```  
  
-   La comparaison de deux caractères inconnus doit être effectuée à l'aide de l'une des macros définies dans Mbstring.h :  
  
    ```  
    if( !_mbccmp( sz1, sz2) )  
    ```  
  
     Ainsi, les deux octets d'un caractère codé sur deux octets sont comparés pour savoir s'ils sont égaux.  
  
## Voir aussi  
 [Conseils de programmation MBCS](../text/mbcs-programming-tips.md)   
 [Dépassement de capacité du tampon](../text/buffer-overflow.md)