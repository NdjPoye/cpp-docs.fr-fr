---
title: "Test de caract&#232;re | Microsoft Docs"
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
ms.assetid: 376ba061-bae3-427e-9569-33fa5949a199
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Test de caract&#232;re
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 4.3.1** Les jeux de caractères testés par les fonctions `isalnum`, `isalpha`, `iscntrl`, `islower`, `isprint` et `isupper`  
  
 La liste suivante décrit ces fonctions telles qu'elles sont implémentées par le compilateur Microsoft C.  
  
|Fonction|Tests des|  
|--------------|---------------|  
|`isalnum`|Caractères 0 à 9, A\-Z, a\-z ASCII 48\-57, 65\-90, 97\-122|  
|`isalpha`|Caractères A–Z, a–z ASCII 65–90, 97–122|  
|`iscntrl`|ASCII 0–31, 127|  
|`islower`|Caractères a–z ASCII 97–122|  
|`isprint`|Caractères A–Z, a–z, 0–9, ponctuation, espace ASCII 32–126|  
|`isupper`|Caractères A–Z ASCII 65–90|  
  
## Voir aussi  
 [Fonctions des bibliothèques](../c-language/library-functions.md)