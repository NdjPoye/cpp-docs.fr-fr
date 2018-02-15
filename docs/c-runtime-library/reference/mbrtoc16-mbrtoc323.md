---
title: mbrtoc16, mbrtoc323 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- mbrtoc16
- mbrtoc32
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mbrtoc16
- mbrtoc32
- uchar/mbrtoc16
- uchar/mbrtoc32
dev_langs:
- C++
helpviewer_keywords:
- mbrtoc16 function
- mbrtoc32 function
ms.assetid: 099ade4d-56f7-4e61-8b45-493f1d7a64bd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7e686a39266587fdc214ddbb0757672a57b94314
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="mbrtoc16-mbrtoc32"></a>mbrtoc16, mbrtoc32
Traduit le premier caractère multioctet dans une chaîne étroite en caractère équivalent UTF-16 ou UTF-32.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
size_t mbrtoc16(   
   char16_t* destination,   
   const char* source,   
   size_t max_bytes,   
   mbstate_t* state   
);  
  
size_t mbrtoc32(  
   char32_t* destination,   
   const char* source,   
   size_t max_bytes,   
   mbstate_t* state   
);  
  
```  
  
#### <a name="parameters"></a>Paramètres  
 `destination`  
 Pointeur vers le `char16_t` ou `char32_t` équivalent du caractère multioctet à convertir. Si vous spécifiez la valeur null, la fonction ne stocke pas de valeur.  
  
 `source`  
 Pointeur vers la chaîne de caractères multioctets à convertir.  
  
 `max_bytes`  
 Nombre maximal d’octets dans `source` à examiner pour rechercher un caractère à convertir. Cette valeur doit être comprise entre 1 et le nombre d’octets, y compris toute marque de fin null, restant dans `source`.  
  
 `state`  
 Pointeur vers un objet d’état de conversion `mbstate_t` utilisé pour interpréter la chaîne multioctets à un ou plusieurs caractères de sortie.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne la valeur de la première de ces conditions qui s’applique, étant donné la valeur `state` actuelle :  
  
|Value|Condition|  
|-----------|---------------|  
|0|Les `max_bytes` (ou moins) caractères suivants convertis à partir de `source` correspondent au caractère large null, qui est la valeur stockée si `destination` n’est pas null.<br /><br /> `state` contient l’état de décalage initial.|  
|Entre 1 et `max_bytes`, inclusif|La valeur retournée est le nombre d’octets de `source` qui terminent un caractère multioctet valide. Les caractères larges convertis sont stockés si `destination` n’est pas null.|  
|-3|Le caractère large suivant résultant d’un appel précédent à la fonction a été stocké dans `destination` si `destination` n’est pas null. Aucun octet de `source` n’est utilisé par cet appel à la fonction.<br /><br /> Lorsque  `source` pointe vers un caractère multioctet dont la représentation nécessite plusieurs caractères larges (par exemple une paire de substitution), la valeur `state` est mise à jour pour que l’appel de fonction suivant écrive le caractère supplémentaire.|  
|-2|Les `max_bytes` octets suivants représentent un caractère multioctet incomplet, mais potentiellement valide. Aucune valeur n’est stockée dans `destination`. Ce résultat peut se produire si `max_bytes` est égal à zéro.|  
|-1|Une erreur d’encodage s’est produite. Les `max_bytes` (ou moins) octets suivants ne contribuent pas à un caractère multioctet complet et valide. Aucune valeur n’est stockée dans `destination`.<br /><br /> `EILSEQ` est stocké dans `errno` et l’état de conversion `state` est non spécifié.|  
  
## <a name="remarks"></a>Notes  
 La fonction `mbrtoc16` lit jusqu’à `max_bytes` octets à partir de `source` pour rechercher le premier caractère multioctet complet et valide, puis elle stocke le caractère UTF-16 équivalent dans `destination`. Les octets sources sont interprétés en fonction des paramètres régionaux multioctets du thread actif. Si le caractère multioctet nécessite plusieurs caractères de sortie UTF-16, par exemple s’il s’agit d’une paire de substitution, la valeur `state` stocke le caractère UTF-16 suivant dans `destination` lors du prochain appel à `mbrtoc16`. La fonction `mbrtoc32` est identique, mais la sortie est stockée comme caractère UTF-32.  
  
 Si `source` est null, ces fonctions retournent l’équivalent d’un appel effectué à l’aide des arguments `NULL` pour `destination`, `""` pour `source`et `1` pour `max_bytes`. Les valeurs passées de `destination` et `max_bytes` sont ignorées.  
  
 Si `source` n’est pas null, la fonction commence au début de la chaîne et elle inspecte jusqu’à `max_bytes` octets pour déterminer le nombre d’octets nécessaires pour terminer le caractère multioctet suivant, y compris les séquences de décalage. Si les octets examinés contiennent un caractère multioctet valide et complet, la fonction convertit le caractère en caractères larges 16 bits ou 32 bits équivalents. Si `destination` n’est pas null, la fonction stocke le premier (et éventuellement unique) caractère résultant dans la destination. Si des caractères de sortie supplémentaires sont nécessaires, une valeur est définie dans `state`. Ainsi, les appels suivants à la fonction génèrent les caractères supplémentaires et retournent la valeur -3. Si aucun autre caractère de sortie n’est nécessaire, `state` est définie à l’état de décalage initial.  
  
## <a name="requirements"></a>Configuration requise  
  
|Fonction|En-tête C|En-tête C++|  
|--------------|--------------|------------------|  
|`mbrtoc16`,                `mbrtoc32`|\<uchar.h>|\<cuchar>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [c16rtomb, c32rtomb](../../c-runtime-library/reference/c16rtomb-c32rtomb1.md)   
 [mbrtowc](../../c-runtime-library/reference/mbrtowc.md)   
 [mbsrtowcs](../../c-runtime-library/reference/mbsrtowcs.md)   
 [mbsrtowcs_s](../../c-runtime-library/reference/mbsrtowcs-s.md)