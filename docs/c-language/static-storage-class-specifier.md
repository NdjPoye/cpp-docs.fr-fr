---
title: "Spécificateur de classe de stockage static │ Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- static variables, specifier
- storage classes, static
- static storage class specifiers
ms.assetid: 9bce361e-919b-46b9-8148-40d7ab0eb024
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 0a51dfc10ac0ae05a67a280b4b76c2c92eb57a0b
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="static-storage-class-specifier"></a>Spécificateur de classe de stockage static
Une variable déclarée au niveau interne avec le spécificateur de classe de stockage **static** a une durée de vie globale, mais est visible uniquement dans le bloc dans lequel elle est déclarée. Pour les chaînes constantes, l’utilisation de **static** est utile, car elle allège la surcharge liée à l’initialisation fréquente des fonctions souvent appelées.  
  
## <a name="remarks"></a>Remarques  
Si vous n’initialisez pas explicitement une variable **static**, elle est initialisée sur 0 par défaut. Dans une fonction, **static** provoque l’allocation du stockage et sert de définition. Les variables statiques internes fournissent du stockage permanent, privé visible uniquement à une fonction unique.  
  
## <a name="see-also"></a>Voir aussi  
[Classes de stockage C](c-storage-classes.md)  
[Classes de stockage (C++)](../cpp/storage-classes-cpp.md)  
