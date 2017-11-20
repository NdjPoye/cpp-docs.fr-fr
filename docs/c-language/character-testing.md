---
title: "Test de caractère | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 376ba061-bae3-427e-9569-33fa5949a199
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 89f48346d9b96c7de20c11fd4cbcde106571ed57
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="character-testing"></a>Test de caractère
**ANSI 4.3.1** Les jeux de caractères testés par les fonctions `isalnum`, `isalpha`, `iscntrl`, `islower`, `isprint` et `isupper`  
  
 La liste suivante décrit ces fonctions telles qu'elles sont implémentées par le compilateur Microsoft C.  
  
|Fonction|Tests des|  
|--------------|---------------|  
|`isalnum`|Caractères 0 à 9, A-Z, a-z ASCII 48-57, 65-90, 97-122|  
|`isalpha`|Caractères A-Z, a-z ASCII 65-90, 97-122|  
|`iscntrl`|ASCII 0 -31, 127|  
|`islower`|Caractères a-z ASCII 97-122|  
|`isprint`|Caractères A-Z, a-z, 0-9, ponctuation, espace ASCII 32-126|  
|`isupper`|Caractères A-Z ASCII 65-90|  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions des bibliothèques](../c-language/library-functions.md)