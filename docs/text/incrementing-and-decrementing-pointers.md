---
title: "Incr&#233;mentation et d&#233;cr&#233;mentation de pointeurs | Microsoft Docs"
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
  - "décrémenter les pointeurs"
  - "incrémenter les pointeurs"
  - "MBCS (C++), pointeurs"
  - "pointeurs (C++), caractères multioctets"
ms.assetid: 0872b4a0-e2bd-4004-8319-070efb76f2fd
caps.latest.revision: 7
caps.handback.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Incr&#233;mentation et d&#233;cr&#233;mentation de pointeurs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez les conseils suivants :  
  
-   Pointez vers les octets de tête et non vers les octets de queue.  Il n'est pas prudent de pointer vers un octet de queue.  Il est plus sûr d'analyser une chaîne vers l'avant que vers l'arrière.  
  
-   Il existe des fonctions et des macros d'incrémentation\/décrémentation de pointeur disponibles pour se déplacer d'un caractère entier :  
  
    ```  
    sz1++;  
    ```  
  
     devient :  
  
    ```  
    sz1 = _mbsinc( sz1 );  
    ```  
  
     Les fonctions `_mbsinc` et `_mbsdec` incrémentent et décrémentent des unités `character`, quelle que soit la taille du caractère.  
  
-   Pour les décréments, vous avez besoin d'un pointeur vers la tête de la chaîne, comme dans l'exemple suivant :  
  
    ```  
    sz2--;  
    ```  
  
     devient :  
  
    ```  
    sz2 = _mbsdec( sz2Head, sz2 );  
    ```  
  
     Votre pointeur de tête peut pointer vers un caractère valide dans la chaîne, par exemple  
  
    ```  
    sz2Head < sz2  
    ```  
  
     Vous devez disposer d'un pointeur vers un octet de tête valide connu.  
  
-   Vous pouvez conserver un pointeur vers le caractère précédent pour des appels plus rapides à `_mbsdec`.  
  
## Voir aussi  
 [Conseils de programmation MBCS](../text/mbcs-programming-tips.md)   
 [Indices d'octets](../text/byte-indices.md)