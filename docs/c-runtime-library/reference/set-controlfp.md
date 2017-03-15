---
title: _set_controlfp | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _set_controlfp
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
- set_controlfp
- _set_controlfp
dev_langs:
- C++
helpviewer_keywords:
- set_controlfp function
- floating-point functions, setting control word
- _set_controlfp function
ms.assetid: e0689d50-f68a-4028-a9c1-fb23eedee4ad
caps.latest.revision: 11
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: f7cf06b52624178a3d5bbe5907289eab7f57cbb5
ms.lasthandoff: 02/24/2017

---
# <a name="setcontrolfp"></a>_set_controlfp
Définit le mot de contrôle à virgule flottante.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void __cdecl _set_controlfp(  
    unsigned int newControl,  
    unsigned int mask  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `newControl`  
 Nouvelles valeurs en bits du mot de contrôle.  
  
 `mask`  
 Masque des bits du nouveau mot de contrôle à définir.  
  
## <a name="return-value"></a>Valeur de retour  
 Aucun  
  
## <a name="remarks"></a>Notes  
 La fonction `_set_controlfp` est similaire à `_control87`, mais elle affecte uniquement au mot de contrôle à virgule flottante la valeur `newControl`. Les bits contenus dans les valeurs indiquent l’état de contrôle à virgule flottante. L’état de contrôle à virgule flottante permet au programme de modifier les modes de précision, d’arrondi et d’infini dans le package mathématique à virgule flottante. Vous pouvez aussi masquer ou démasquer les exceptions de virgule flottante à l’aide de `_set_controlfp`. Pour plus d’informations, consultez [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md).  
  
 Cette fonction est déconseillée lors de la compilation avec [/clr (Compilation pour le Common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md) , car le common language runtime prend uniquement en charge la précision en virgule flottante par défaut.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|Compatibilité|  
|-------------|---------------------|-------------------|  
|`_set_controlfp`|\<float.h>|Processeur x86 uniquement|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [_clear87, _clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [_status87, _statusfp, _statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)
