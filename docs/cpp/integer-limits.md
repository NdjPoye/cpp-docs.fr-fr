---
title: "Limites d&#39;entier | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "limites d'entier"
  - "limites intégrales"
  - "limites, entiers"
  - "LIMITS.H (fichier d'en-tête)"
ms.assetid: 6922bdbf-0f49-443b-bc03-ee182e4cbd57
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Limites d&#39;entier
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Les limites pour les types d'entiers sont répertoriées dans le tableau ci\-dessous.  Ces limites sont également définies dans le fichier d'en\-tête standard LIMITS.H.  
  
### Limites appliquées aux constantes entières  
  
|Constante|Signification|Valeur|  
|---------------|-------------------|------------|  
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
|**INT\_MIN**|Valeur minimale d'une variable de type `int`|–2147483648|  
|**INT\_MAX**|Valeur maximale d'une variable de type `int`|2147483647|  
|**UINT\_MAX**|Valeur maximale d'une variable de type `unsigned int`|4294967295 \(0xffffffff\)|  
|**LONG\_MIN**|Valeur minimale d'une variable de type **long**|–2147483648|  
|**LONG\_MAX**|Valeur maximale d'une variable de type **long**|2147483647|  
|**ULONG\_MAX**|Valeur maximale d'une variable de type `unsigned long`|4294967295 \(0xffffffff\)|  
|**\_I64\_MIN**|Valeur minimale d'une variable de type `__int64`|\-9223372036854775808|  
|**\_I64\_MAX**|Valeur maximale d'une variable de type `__int64`|9223372036854775807|  
|**\_UI64\_MAX**|Valeur maximale d'une variable de type **unsigned \_\_int64**|18446744073709551615 \(0xffffffffffffffff\)|  
  
 Si une valeur dépasse la plus grande représentation d'entier, le compilateur Microsoft génère une erreur.  
  
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [Limites des valeurs à virgule flottante](../cpp/floating-limits.md)