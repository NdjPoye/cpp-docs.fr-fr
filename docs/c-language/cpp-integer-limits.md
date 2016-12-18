---
title: "Limites d&#39;entier C++ | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "limites d'entier"
  - "limites, entiers"
  - "limites, constantes entières"
ms.assetid: 0c23cbd6-29fb-4d9c-b689-5984e19748de
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Limites d&#39;entier C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Les limites pour les types d'entiers sont répertoriées dans le tableau ci\-dessous.  Ces limites sont définies dans le fichier d'en\-tête standard LIMITS.H.  Microsoft C permet également la déclaration de variables de type entier dimensionnées, qui sont des types intégraux d'une taille de 8, 16 ou 32 bits.  Pour plus d'informations sur les entiers dimensionnés, consultez [Types d'entiers dimensionnés](../c-language/c-sized-integer-types.md).  
  
### Limites appliquées aux constantes entières  
  
|**Constante**|Signification|Valeur|  
|-------------------|-------------------|------------|  
|**CHAR\_BIT**|Nombre de bits dans la plus petite variable qui n'est pas un champ de bits|8|  
|**SCHAR\_MIN**|Valeur minimale d'une variable de type **signed char**|–128|  
|**SCHAR\_MAX**|Valeur maximale d'une variable de type **signed char**|127|  
|**UCHAR\_MAX**|Valeur maximale d'une variable de type `unsigned char`|255 \(0xff\)|  
|**CHAR\_MIN**|Valeur minimale d'une variable de type `char`|–128 ; 0 si l'option \/J est utilisée|  
|**CHAR\_MAX**|Valeur maximale d'une variable de type `char`|127 ; 255 si l'option \/J est utilisée|  
|**MB\_LEN\_MAX**|Nombre maximal d'octets dans une constante à multiples caractères|5|  
|**SHRT\_MIN**|Valeur minimale d'une variable de type **short**|–32768|  
|**SHRT\_MAX**|Valeur maximale d'une variable de type **short**|32767|  
|**USHRT\_MAX**|Valeur maximale d'une variable de type **unsigned short**|65535 \(0xffff\)|  
|**INT\_MIN**|Valeur minimale d'une variable de type `int`|–2147483647 – 1|  
|**INT\_MAX**|Valeur maximale d'une variable de type `int`|2147483647|  
|**UINT\_MAX**|Valeur maximale d'une variable de type `unsigned int`|4294967295 \(0xffffffff\)|  
|**LONG\_MIN**|Valeur minimale d'une variable de type **long**|–2147483647 – 1|  
|**LONG\_MAX**|Valeur maximale d'une variable de type **long**|2147483647|  
|**ULONG\_MAX**|Valeur maximale d'une variable de type `unsigned long`|4294967295 \(0xffffffff\)|  
  
 Si une valeur dépasse la plus grande représentation d'entier, le compilateur Microsoft génère une erreur.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Constantes entières C](../c-language/c-integer-constants.md)