---
title: "Incrémentation et décrémentation de pointeurs | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- incrementing pointers
- MBCS [C++], pointers
- pointers [C++], multibyte characters
- decrementing pointers
ms.assetid: 0872b4a0-e2bd-4004-8319-070efb76f2fd
caps.latest.revision: "7"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e9eccf65f091c8c5c273f6a65cb7e81b0d386afa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="incrementing-and-decrementing-pointers"></a>Incrémentation et décrémentation de pointeurs
Utilisez les conseils suivants :  
  
-   Pointer vers les octets de tête, pas les octets de Queue. Il est prudent de disposer d’un pointeur vers un octet de fin. Il est généralement plus sûr d’analyser une chaîne vers l’avant, plutôt que dans l’ordre inverse.  
  
-   Il existe des fonctions d’incrémentation/décrémentation de pointeur et les macros qui se déplacent d’un caractère entier :  
  
    ```  
    sz1++;  
    ```  
  
     Devient :  
  
    ```  
    sz1 = _mbsinc( sz1 );  
    ```  
  
     Le `_mbsinc` et `_mbsdec` fonctions correctement incrémenter et décrémenter dans `character` unités, quelles que soient la taille de caractères.  
  
-   Pour décrémente, vous avez besoin d’un pointeur vers le début de la chaîne, comme suit :  
  
    ```  
    sz2--;  
    ```  
  
     Devient :  
  
    ```  
    sz2 = _mbsdec( sz2Head, sz2 );  
    ```  
  
     Vous pouvez également votre pointeur de tête peut être un caractère valide dans la chaîne, telles que :  
  
    ```  
    sz2Head < sz2  
    ```  
  
     Vous devez disposer d’un pointeur vers un octet de tête valide connu.  
  
-   Vous pouvez souhaiter conserver un pointeur vers le caractère précédent pour des appels plus rapides à `_mbsdec`.  
  
## <a name="see-also"></a>Voir aussi  
 [Conseils de programmation MBCS](../text/mbcs-programming-tips.md)   
 [Indices d’octets](../text/byte-indices.md)