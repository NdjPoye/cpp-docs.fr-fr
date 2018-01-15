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
ms.workload: cplusplus
ms.openlocfilehash: 28c2cd3a2e868a595d73d06b5cae8e71ec8cc313
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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