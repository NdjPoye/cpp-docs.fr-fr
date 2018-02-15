---
title: feraiseexcept | Microsoft Docs
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
- feraiseexcept
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
apitype: HeaderDef
f1_keywords:
- feraiseexcept
- fenv/feraiseexcept
dev_langs:
- C++
helpviewer_keywords:
- feraiseexcept function
ms.assetid: 87e89151-83c2-4563-9a9a-45666245d437
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: aaaa1848af2c8a7831017f6332afa988c305fe05
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="feraiseexcept"></a>feraiseexcept
Déclenche les exceptions de virgule flottante spécifiées.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int feraiseexcept(  
   int excepts  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `excepts`  
 Exceptions de virgule flottante à déclencher.  
  
## <a name="return-value"></a>Valeur de retour  
 Si toutes les exceptions spécifiées sont correctement déclenchées, retourne 0.  
  
## <a name="remarks"></a>Notes  
 La fonction `feraiseexcept` tente de déclencher les exceptions de virgule flottante spécifiées par `excepts`.   La fonction `feraiseexcept` prend en charge les macros d’exception suivantes, définies dans \<fenv.h> :  
  
|Macros d’exception|Description|  
|---------------------|-----------------|  
|FE_DIVBYZERO|Une erreur de singularité ou de pôle s’est produite dans une opération à virgule flottante précédente ; une valeur infinie a été créée.|  
|FE_INEXACT|La fonction a été forcée d’arrondir le résultat stocké d’une opération à virgule flottante précédente.|  
|FE_INVALID|Une erreur de domaine s’est produite pendant une opération à virgule flottante précédente.|  
|FE_OVERFLOW|Une erreur de plage s’est produite ; le résultat d’une opération à virgule flottante précédente était trop grand pour être représenté.|  
|FE_UNDERFLOW|Le résultat d’une opération à virgule flottante précédente était trop petit pour être représenté avec une précision complète ; une valeur dénormalisée a été créée.|  
|FE_ALLEXCEPT|Opération OR au niveau du bit de toutes les exceptions de virgule flottante prises en charge.|  
  
 L’argument `excepts` peut être zéro, l’une des valeurs de macro d’exception ou l’opération OR au niveau du bit d’au moins deux macros d’exception prises en charge. Si une des macros d’exception spécifiées est FE_OVERFLOW ou FE_UNDERFLOW, l’exception FE_INEXACT peut être déclenchée en tant qu’effet secondaire.  
  
 Pour utiliser cette fonction, vous devez désactiver les optimisations à virgule flottante qui peuvent empêcher l’accès à l’aide de la directive `#pragma fenv_access(on)` avant l’appel. Pour plus d'informations, consultez [fenv_access](../../preprocessor/fenv-access.md).  
  
 **Section spécifique à Microsoft :** les exceptions spécifiées dans `excepts` sont déclenchées dans l’ordre FE_INVALID, FE_DIVBYZERO, FE_OVERFLOW, FE_UNDERFLOW, FE_INEXACT. Toutefois, FE_INEXACT peut être déclenchée quand FE_OVERFLOW ou FE_UNDERFLOW est déclenchée, même si elle n’est pas spécifiée dans `excepts`. **Fin de la section spécifique à Microsoft**  
  
## <a name="requirements"></a>Configuration requise  
  
|Fonction|En-tête C|En-tête C++|  
|--------------|--------------|------------------|  
|`feraiseexcept`|\<fenv.h>|\<cfenv>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fesetexceptflag](../../c-runtime-library/reference/fesetexceptflag2.md)   
 [feholdexcept](../../c-runtime-library/reference/feholdexcept2.md)   
 [fetestexcept](../../c-runtime-library/reference/fetestexcept1.md)   
 [feupdateenv](../../c-runtime-library/reference/feupdateenv.md)