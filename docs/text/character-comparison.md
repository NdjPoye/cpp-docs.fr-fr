---
title: "Comparaison de caractères | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- comparing characters
- MBCS [C++], character comparison
- characters [C++], comparing
ms.assetid: 18846e44-3e6e-40c4-9b42-3153fb15db20
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 0b9098dc20c33cccfd64631e7732be0128cb5bb0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="character-comparison"></a>Comparaison de caractères
Utilisez les conseils suivants :  
  
-   Comparaison d’un octet de tête connu par un caractère ASCII fonctionne correctement :  
  
    ```  
    if( *sz1 == 'A' )  
    ```  
  
-   Comparaison de deux caractères inconnus nécessite l’utilisation de l’une des macros définies dans Mbstring.h :  
  
    ```  
    if( !_mbccmp( sz1, sz2) )  
    ```  
  
     Cela garantit que les deux octets d’un caractère sur deux octets sont comparés pour l’égalité.  
  
## <a name="see-also"></a>Voir aussi  
 [Conseils de programmation MBCS](../text/mbcs-programming-tips.md)   
 [Dépassement de mémoire tampon](../text/buffer-overflow.md)