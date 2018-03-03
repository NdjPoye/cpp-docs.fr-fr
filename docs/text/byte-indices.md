---
title: "Indices d’octets | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MBCS [C++], byte indices
- byte indices [C++]
ms.assetid: f6e7774a-86c6-41c2-89e3-74fd46432e47
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 594acadeedad06e9720180c38bd0bcd657391879
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="byte-indices"></a>Indices d'octets
Utilisez les conseils suivants :  
  
-   Travail avec des index dans une chaîne présente des problèmes semblables à ceux posés par la manipulation du pointeur. Considérez cet exemple, qui analyse une chaîne d’un caractère de barre oblique inverse :  
  
    ```  
    while ( rgch[ i ] != '\\' )  
        i++;  
    ```  
  
     Cela peut indexer un octet de fin, et non un octet de tête, et par conséquent, elle ne peut pas pointer sur un `character`.  
  
-   Utilisez le [_mbclen](../c-runtime-library/reference/mbclen-mblen-mblen-l.md) afin de résoudre le problème précédent :  
  
    ```  
    while ( rgch[ i ] != '\\' )  
        i += _mbclen ( rgch + i );  
    ```  
  
     Ce code indexe correctement un octet de tête, par conséquent, pour un `character`. Le `_mbclen` fonction détermine la taille d’un caractère (1 ou 2 octets).  
  
## <a name="see-also"></a>Voir aussi  
 [Conseils de programmation MBCS](../text/mbcs-programming-tips.md)   
 [Dernier caractère d’une chaîne](../text/last-character-in-a-string.md)