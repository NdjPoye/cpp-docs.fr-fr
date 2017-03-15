---
title: feupdateenv | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- feupdateenv
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
- feupdateenv
- fenv/feupdateenv
dev_langs:
- C++
helpviewer_keywords:
- feupdateenv function
ms.assetid: 3d170042-dfd5-4e4f-a55f-038cf2296cc9
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 170e385a5741ced5612c060a7a537a05b4668432
ms.lasthandoff: 02/24/2017

---
# <a name="feupdateenv"></a>feupdateenv
Enregistre les exceptions de virgule flottante déclenchées, restaure l’état de l’environnement à virgule flottante spécifié, puis lève les exceptions de virgule flottante enregistrées.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int feupdateenv(  
   const fenv_t* penv  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `penv`  
 Pointeur désignant un objet `fenv_t` qui contient un environnement à virgule flottante tel que défini par un appel à [fegetenv](http://msdn.microsoft.com/Library/61df848d-6ba8-4c6e-be35-216436fe7736) ou [feholdexcept](http://msdn.microsoft.com/Library/c286ace3-ec39-482a-be8b-f998d31003d9). Vous pouvez également spécifier l’environnement à virgule flottante de démarrage par défaut à l’aide de la macro FE_DFL_ENV.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne 0 si toutes les actions se sont déroulées correctement.        Sinon, retourne une valeur différente de zéro.  
  
## <a name="remarks"></a>Notes  
 La fonction `feupdateenv` effectue plusieurs actions. Tout d’abord, elle stocke automatiquement les indicateurs d’état d’exception de virgule flottante déclenchés actuels. Ensuite, elle définit l’environnement à virgule flottante actuel à partir de la valeur stockée dans l’objet `fenv_t` désigné par `penv`. Si `penv` n’est pas FE_DFL_ENV ou ne désigne pas un objet `fenv_t` valide, le comportement suivant n’est pas défini. Enfin, `feupdateenv` déclenche les exceptions de virgule flottante stockées localement.  
  
 Pour utiliser cette fonction, vous devez désactiver les optimisations à virgule flottante qui peuvent empêcher l’accès à l’aide de la directive `#pragma fenv_access(on)` avant l’appel. Pour plus d’informations, consultez [fenv_access](../../preprocessor/fenv-access.md).  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête C|En-tête C++|  
|--------------|--------------|------------------|  
|`feupdateenv`|\<fenv.h>|\<cfenv>|  
  
 Pour plus d’informations sur la compatibilité, voir consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [fegetenv](../../c-runtime-library/reference/fegetenv1.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [feholdexcept](../../c-runtime-library/reference/feholdexcept2.md)   
 [fesetexceptflag](../../c-runtime-library/reference/fesetexceptflag2.md)
