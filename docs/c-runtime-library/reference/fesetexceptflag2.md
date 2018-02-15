---
title: fesetexceptflag2 | Microsoft Docs
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
- fesetexceptflag
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
- fesetexceptflag
- fenv/fesetexceptflag
dev_langs:
- C++
helpviewer_keywords:
- fesetexceptflag function
ms.assetid: 2f7dad77-9e54-4097-a3e3-35176ace4de5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 24aff3007d88f9ae5ebc30811e652284ecebeba5
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="fesetexceptflag"></a>fesetexceptflag
Définit les indicateurs d’état à virgule flottante spécifiés dans l’environnement à virgule flottante actuel.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int fesetexceptflag(  
     const fexcept_t *pstatus,  
     int excepts  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pstatus`  
 Pointeur désignant un objet `fexcept_t` qui contient les valeurs sur lesquelles définir des indicateurs d’état d’exception. L’objet peut être défini par un appel précédent à [fegetexceptflag](fegetexceptflag2.md).  
  
 `excepts`  
 Indicateurs d’état d’exception de virgule flottante à définir.  
  
## <a name="return-value"></a>Valeur de retour  
 Si tous les indicateurs d’état d’exception spécifiés sont définis correctement, retourne 0. Sinon, retourne une valeur différente de zéro.  
  
## <a name="remarks"></a>Notes  
 La fonction `fesetexceptflag` définit l’état des indicateurs d’état d’exception de virgule flottante spécifiés par `excepts` sur les valeurs correspondantes définies dans l’objet `fexcept_t` désigné par `pstatus`.  Elle ne déclenche pas les exceptions. Le pointeur `pstatus` doit désigner un objet `fexcept_t` valide ; sinon, le comportement suivant n’est pas défini. La fonction `fesetexceptflag` prend en charge les valeurs de macros d’exception suivantes dans `excepts`, définies dans \<fenv.h> :  
  
|Macros d’exception|Description|  
|---------------------|-----------------|  
|FE_DIVBYZERO|Une erreur de singularité ou de pôle s’est produite dans une opération à virgule flottante précédente ; une valeur infinie a été créée.|  
|FE_INEXACT|La fonction a été forcée d’arrondir le résultat stocké d’une opération à virgule flottante précédente.|  
|FE_INVALID|Une erreur de domaine s’est produite pendant une opération à virgule flottante précédente.|  
|FE_OVERFLOW|Une erreur de plage s’est produite ; le résultat d’une opération à virgule flottante précédente était trop grand pour être représenté.|  
|FE_UNDERFLOW|Le résultat d’une opération à virgule flottante précédente était trop petit pour être représenté avec une précision complète ; une valeur dénormalisée a été créée.|  
|FE_ALLEXCEPT|Opération OR au niveau du bit de toutes les exceptions de virgule flottante prises en charge.|  
  
 L’argument `excepts` peut être zéro, l’une des macros d’exception de virgule flottante prises en charge ou l’opération OR au niveau du bit d’au moins deux macros. L’effet de toute autre valeur d’argument est indéfini.  
  
 Pour utiliser cette fonction, vous devez désactiver les optimisations à virgule flottante qui peuvent empêcher l’accès à l’aide de la directive `#pragma fenv_access(on)` avant l’appel. Pour plus d'informations, consultez [fenv_access](../../preprocessor/fenv-access.md).  
  
## <a name="requirements"></a>Configuration requise  
  
|Fonction|En-tête C|En-tête C++|  
|--------------|--------------|------------------|  
|`fesetexceptflag`|\<fenv.h>|\<cfenv>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fegetexceptflag](../../c-runtime-library/reference/fegetexceptflag2.md)