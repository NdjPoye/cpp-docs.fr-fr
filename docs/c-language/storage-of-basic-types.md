---
title: "Stockage de types de base | Microsoft Docs"
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
helpviewer_keywords: 
  - "opérations arithmétiques (C++), types"
  - "types de données (C), spécificateurs"
  - "types de données (C), stockage"
  - "double (type de données), stockage"
  - "chiffres à virgule flottante, stockage"
  - "int (type de données)"
  - "types intégraux"
  - "types intégraux, stockage"
  - "long double (mot clé) (C), stockage"
  - "long (mot clé) (C)"
  - "short (type de données)"
  - "types signés (C++), stockage"
  - "spécificateurs (C++), type"
  - "stockage (C++), types"
  - "types de stockage (C++)"
  - "spécificateurs de type (C++), tailles"
  - "types (C), arithmétiques"
  - "types non signés (C++), stockage"
ms.assetid: bd1f33c1-c6b9-4558-8a72-afb21aef3318
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Stockage de types de base
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le tableau suivant résume le stockage associé à chaque type de base.  
  
### Tailles des types fondamentaux  
  
|Type|Stockage|  
|----------|--------------|  
|`char`, `unsigned char`, **signed char**|1 octet|  
|**short**, **unsigned short**|2 octets|  
|`int`, `unsigned int`|4 octets|  
|**long**, `unsigned long`|4 octets|  
|**float**|4 octets|  
|**double**|8 octets|  
|`long double`|8 octets|  
  
 Les types de données C sont répartis dans des catégories générales.  Les « types intégraux » incluent `char`, `int`, **short**, **long**, **signed**, `unsigned` et `enum`.  Les « types flottants » sont **float**, **double** et `long double`.  Les « types arithmétiques » incluent tous les types flottants et intégraux.  
  
## Voir aussi  
 [Déclarations et types](../c-language/declarations-and-types.md)