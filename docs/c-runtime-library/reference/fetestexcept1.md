---
title: fetestexcept1 | Microsoft Docs
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
- fetestexcept
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fetestexcept
- fenv/fetestexcept
dev_langs:
- C++
helpviewer_keywords:
- fetestexept function
ms.assetid: ca4dc43f-5573-440d-bc19-ead7571b13dc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8f70e78e515e50b00992a22eb01988e09a5ccd42
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="fetestexcept"></a>fetestexcept
Détermine les indicateurs d’état d’exception de virgule flottante spécifiés qui sont définis.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int fetestexcept(  
   int excepts  
);  
  
```  
  
#### <a name="parameters"></a>Paramètres  
 `excepts`  
 Opération OR au niveau du bit des indicateurs d’état à virgule flottante à tester.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne un masque de bits qui contient une opération OR au niveau du bit des macros d’exception de virgule flottante qui correspondent aux indicateurs d’état d’exception définis. Retourne 0 si aucune des exceptions n’est définie.  
  
## <a name="remarks"></a>Notes  
 La fonction fetestexcept permet de déterminer les exceptions levées par une opération à virgule flottante. Utilisez le paramètre `excepts` pour spécifier les indicateurs d’état d’exception à tester. La fonction `fetestexcept` utilise les macros d’exception suivantes définies dans \<fenv.h > dans `excepts` et la valeur de retour :  
  
|Macros d’exception|Description|  
|---------------------|-----------------|  
|FE_DIVBYZERO|Une erreur de singularité ou de pôle s’est produite dans une opération à virgule flottante précédente ; une valeur infinie a été créée.|  
|FE_INEXACT|La fonction a été forcée d’arrondir le résultat stocké d’une opération à virgule flottante précédente.|  
|FE_INVALID|Une erreur de domaine s’est produite pendant une opération à virgule flottante précédente.|  
|FE_OVERFLOW|Une erreur de plage s’est produite ; le résultat d’une opération à virgule flottante précédente était trop grand pour être représenté.|  
|FE_UNDERFLOW|Le résultat d’une opération à virgule flottante précédente était trop petit pour être représenté avec une précision complète ; une valeur dénormalisée a été créée.|  
|FE_ALLEXCEPT|Opération OR au niveau du bit de toutes les exceptions de virgule flottante prises en charge.|  
  
 L’argument `excepts` spécifié peut être 0, l’une des macros d’exception de virgule flottante prises en charge ou l’opération OR au niveau du bit d’au moins deux macros. L’effet de toute autre valeur d’argument `excepts` est indéfini.  
  
 Pour utiliser cette fonction, vous devez désactiver les optimisations à virgule flottante qui peuvent empêcher l’accès à l’aide de la directive `#pragma fenv_access(on)` avant l’appel. Pour plus d'informations, consultez [fenv_access](../../preprocessor/fenv-access.md).  
  
## <a name="requirements"></a>Configuration requise  
  
|Fonction|En-tête C|En-tête C++|  
|--------------|--------------|------------------|  
|`fetestexcept`|\<fenv.h>|\<cfenv>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [feraiseexcept](../../c-runtime-library/reference/feraiseexcept.md)