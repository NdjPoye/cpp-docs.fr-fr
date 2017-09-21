---
title: Stockage des types de base | Microsoft Docs
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
- specifiers [C++], type
- integral types, storage
- storage [C++], types
- floating-point numbers, storage
- type specifiers [C++], sizes
- arithmetic operations [C++], types
- int data type
- short data type
- signed types [C++], storage
- long double keyword [C], storage
- long keyword [C]
- double data type, storage
- types [C], arithmetic
- integral types
- data types [C], specifiers
- storing types [C++]
- unsigned types [C++], storage
- data types [C], storage
ms.assetid: bd1f33c1-c6b9-4558-8a72-afb21aef3318
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 5a42f5c0e4592fc397ac51d610ed6ca1495c4504
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="storage-of-basic-types"></a>Stockage de types de base
Le tableau suivant résume le stockage associé à chaque type de base.  
  
### <a name="sizes-of-fundamental-types"></a>Tailles des types fondamentaux  
  
|Type|Stockage|  
|----------|-------------|  
|`char`, `unsigned char`, **signed char**|1 octet|  
|**short**, **unsigned short**|2 octets|  
|`int`, `unsigned int`|4 octets|  
|**long**, `unsigned long`|4 octets|  
|**float**|4 octets|  
|**double**|8 octets|  
|`long double`|8 octets|  
  
 Les types de données C sont répartis dans des catégories générales. Les « types intégraux » incluent `char`, `int`, **short**, **long**, **signed**, `unsigned` et `enum`. Les « types flottants » sont **float**, **double** et `long double`. Les « types arithmétiques » incluent tous les types flottants et intégraux.  
  
## <a name="see-also"></a>Voir aussi  
 [Déclarations et types](../c-language/declarations-and-types.md)