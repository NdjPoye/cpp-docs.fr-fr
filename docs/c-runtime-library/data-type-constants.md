---
title: "Types de donn&#233;es constantes | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "FLT_MIN"
  - "SHRT_MAX"
  - "CHAR_MIN"
  - "MB_LEN_MAX"
  - "DBL_EPSILON"
  - "SHRT_MIN"
  - "_FLT_RADIX"
  - "FLT_DIG"
  - "FLT_MAX_10_EXP"
  - "FLT_MANT_DIG"
  - "DBL_MAX_EXP"
  - "SCHAR_MIN"
  - "SCHAR_MAX"
  - "DBL_MIN"
  - "FLT_MIN_10_EXP"
  - "_DBL_ROUNDS"
  - "USHRT_MAX"
  - "FLT_MAX_EXP"
  - "LONG_MAX"
  - "DBL_MAX"
  - "DBL_DIG"
  - "FLT_MIN_EXP"
  - "INT_MIN"
  - "DBL_MIN_10_EXP"
  - "CHAR_BIT"
  - "INT_MAX"
  - "ULONG_MAX"
  - "DBL_MIN_EXP"
  - "LONG_MIN"
  - "_FLT_ROUNDS"
  - "DBL_MANT_DIG"
  - "_DBL_RADIX"
  - "CHAR_MAX"
  - "FLT_MAX"
  - "DBL_MAX_10_EXP"
  - "UCHAR_MAX"
  - "FLT_EPSILON"
  - "UINT_MAX"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_DBL_RADIX (constante)"
  - "_DBL_ROUNDS (constante)"
  - "_FLT_RADIX (constante)"
  - "_FLT_ROUNDS (constante)"
  - "CHAR_BIT (constante)"
  - "CHAR_MAX (constante)"
  - "CHAR_MIN (constante)"
  - "constantes (C++), type de données"
  - "constantes de types de données (C++)"
  - "DBL_DIG (constante)"
  - "DBL_EPSILON (constante)"
  - "DBL_MANT_DIG (constante)"
  - "DBL_MAX (constante)"
  - "DBL_MAX_10_EXP (constante)"
  - "DBL_MAX_EXP (constante)"
  - "DBL_MIN (constante)"
  - "DBL_MIN_10_EXP (constante)"
  - "DBL_MIN_EXP (constante)"
  - "DBL_RADIX (constante)"
  - "DBL_ROUNDS (constante)"
  - "FLT_DIG (constante)"
  - "FLT_EPSILON (constante)"
  - "FLT_MANT_DIG (constante)"
  - "FLT_MAX (constante)"
  - "FLT_MAX_10_EXP (constante)"
  - "FLT_MAX_EXP (constante)"
  - "FLT_MIN (constante)"
  - "FLT_MIN_10_EXP (constante)"
  - "FLT_MIN_EXP (constante)"
  - "FLT_RADIX (constante)"
  - "FLT_ROUNDS (constante)"
  - "INT_MAX (constante)"
  - "INT_MIN (constante)"
  - "LONG_MAX (constante)"
  - "LONG_MIN (constante)"
  - "MB_LEN_MAX (constante)"
  - "SCHAR_MAX (constante)"
  - "SCHAR_MIN (constante)"
  - "SHRT_MAX (constante)"
  - "SHRT_MIN (constante)"
  - "UCHAR_MAX (constante)"
  - "UINT_MAX (constante)"
  - "ULONG_MAX (constante)"
  - "USHRT_MAX (constante)"
ms.assetid: c0f1c405-0465-41d5-b5ff-e81cdb6f1622
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Types de donn&#233;es constantes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les constantes de type sont les plages de valeurs dépendantes de l'implémentation autorisées pour les types de données intégraux.  Les constantes énumérées ci\-après donnent les plages pour les types de données intégraux et sont définies dans LIMITS.H.  
  
> [!NOTE]
>  L'option \/J du compilateur modifie le paramètre par défaut en remplaçant le type `char`par `unsigned`.  
  
|Constante|Valeur|Signification|  
|---------------|------------|-------------------|  
|**SCHAR\_MAX**|127|Valeur signée maximale `char`|  
|**SCHAR\_MIN**|–128|Valeur minimale signée `char`|  
|**UCHAR\_MAX**|255 \(0xff\)|Valeur maximale `unsigned char`|  
|**CHAR\_BIT**|8|Nombre de bits dans un `char`|  
|**USHRT\_MAX**|65535 \(0xffff\)|Valeur maximale **unsigned short**|  
|**SHRT\_MAX**|32767|Valeur signée maximale **short**|  
|**SHRT\_MIN**|–32768|Valeur signée maximale **short**|  
|**UINT\_MAX**|4294967295 \(0xffffffff\)|Valeur maximale `unsigned int`|  
|**ULONG\_MAX**|4294967295 \(0xffffffff\)|Valeur maximale `unsigned long`|  
|**INT\_MAX**|2147483647|Valeur signée maximale `int`|  
|**INT\_MIN**|–2147483647–1|Valeur minimale signée `int`|  
|**LONG\_MAX**|2147483647|Valeur maximale \(signée\) **long**|  
|**LONG\_MIN**|–2147483647–1|Valeur maximale \(signée\) **long**|  
|**CHAR\_MAX**|127 ; 255 si l'option \/J est utilisée|Valeur maximale `char`|  
|**CHAR\_MIN**|–128 ; 0 si l'option \/J est utilisée|Valeur minimale  `char`|  
|**MB\_LEN\_MAX**|2|Nombre maximal d'octets dans le`char`multioctets|  
|**\_I64\_MAX**|9223372036854775807|Valeur \(signé\) maximale **int64**|  
|**\_I64\_MIN**|\-9223372036854775807\-1|Valeur \(signé\) maximale **int64**|  
|**\_UI64\_MAX**|\(0xffffffffffffffff\)|Valeur \(non signé\) maximale **int64**|  
  
 Les constantes suivantes indiquent la plage et d'autres caractéristiques des types de données  **double** et **float** , et sont définies dans FLOAT.H :  
  
|Constante|Valeur|Description|  
|---------------|------------|-----------------|  
|**DBL\_DIG**|15|\# des chiffres décimaux de précision|  
|**DBL\_EPSILON**|2.2204460492503131e\-016|Les plus petits tels que 1.0\+**DBL\_EPSILON** \! \=1.0|  
|**DBL\_MANT\_DIG**|53|\# de bits de la mantisse|  
|**DBL\_MAX**|1.7976931348623158e\+308|Valeur maximale|  
|**DBL\_MAX\_10\_EXP**|308|Exposant décimale maximal|  
|**DBL\_MAX\_EXP**|1024|Exposant binaire maximal|  
|**DBL\_MIN**|2.2250738585072014e\-308|Valeur positive minimale.|  
|**DBL\_MIN\_10\_EXP**|\(\-307\)|Exposant décimale minimal|  
|**DBL\_MIN\_EXP**|\(–1021\)|Exposant binaire minimal|  
|**\_DBL\_RADIX**|2|Base d'exposant|  
|**\_DBL\_ROUNDS**|1|Ajout d'arrondi : près de|  
|**FLT\_DIG**|6|Nombre de chiffres décimaux de la précision|  
|**FLT\_EPSILON**|1.192092896e\-07F|Les plus petits tels que 1.0\+**FLT\_EPSILON** \! \=1.0|  
|**FLT\_MANT\_DIG**|24|Nombre de bits de la mantisse|  
|**FLT\_MAX**|3.402823466e\+38F|Valeur maximale|  
|**FLT\_MAX\_10\_EXP**|38|Exposant décimale maximal|  
|**FLT\_MAX\_EXP**|128|Exposant binaire maximal|  
|**FLT\_MIN**|1.175494351e\-38F|Valeur positive minimale.|  
|**FLT\_MIN\_10\_EXP**|\(–37\)|Exposant décimale minimal|  
|**FLT\_MIN\_EXP**|\(–125\)|Exposant binaire minimal|  
|**FLT\_RADIX**|2|Base d'exposant|  
|**FLT\_ROUNDS**|1|Ajout d'arrondi : près de|  
  
## Voir aussi  
 [Constantes globales](../c-runtime-library/global-constants.md)