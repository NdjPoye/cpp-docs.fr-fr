---
title: "Types de données SBCS et MBCS | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MBCS
- SBCS
dev_langs: C++
helpviewer_keywords:
- SBCS and MBCS data types
- data types [C], MBCS and SBCS
ms.assetid: 4c3ef9da-e397-48d4-800e-49dba36db171
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c54b6e9716e7f0aee9a0b211148b76804d9520bf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="sbcs-and-mbcs-data-types"></a>Types de données SBCS et MBCS
Toute routine de bibliothèque Runtime `MBCS` Microsoft qui gère un seul caractère multi-octet ou un seul octet de caractère multi-octet attend un argument `unsigned int` (où 0x00 <= valeur du caractère <= 0xFFFF et 0x00 <= valeur de l’octet <= 0xFF). Une routine `MBCS` qui gère des octets ou caractères multi-octets dans un contexte de chaîne attend une chaîne de caractères multi-octets représentée en tant que pointeur `unsigned char`.  
  
> [!CAUTION]
>  Chaque octet d’un caractère multi-octet peut être représenté dans un `char` 8 bits. Toutefois, un caractère codé sur un octet `SBCS` ou `MBCS` de type `char` avec une valeur supérieure à 0x7F est négatif. Quand un tel caractère est converti directement en `int` ou `long`, le compilateur génère un résultat de type signe étendu, ce qui peut donc donner des résultats inattendus.  
  
 Ainsi, il est préférable de représenter un octet d’un caractère multi-octet sous forme de `unsigned char` 8 bits. Ou, pour éviter un résultat négatif, il suffit de convertir un caractère codé sur un octet de type `char` en `unsigned char` avant de le convertir en `int` ou `long`.  
  
 Étant donné que certaines fonctions de gestion des chaînes `SBCS` acceptent des paramètres `char*` (signés), un avertissement du compilateur d’incompatibilité de type est généré quand `_MBCS` est défini. Il existe trois façons d’éviter cet avertissement, indiquées dans l’ordre de leur efficacité :  
  
1.  Utilisez les fonctions inline « de type sécurisé » dans TCHAR.H. Il s'agit du comportement par défaut.  
  
2.  Utilisez les macros « directes » dans TCHAR.H en définissant `_MB_MAP_DIRECT` sur la ligne de commande. Ce faisant, vous devez associer manuellement les types. Cette méthode est la plus rapide mais n’est pas de type sécurisé.  
  
3.  Utilisez les fonctions de bibliothèque liée statiquement « de type sécurisé » dans TCHAR.H. Pour cela, définissez la constante `_NO_INLINING` sur la ligne de commande. Cette méthode est la plus lente, mais la plus sécurisée pour le type.  
  
## <a name="see-also"></a>Voir aussi  
 [Internationalisation](../c-runtime-library/internationalization.md)   
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)