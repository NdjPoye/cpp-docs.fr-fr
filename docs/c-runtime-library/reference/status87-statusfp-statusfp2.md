---
title: _status87, _statusfp, _statusfp2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _statusfp2
- _statusfp
- _status87
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
- _statusfp2
- _statusfp
- statusfp2
- _status87
- status87
- statusfp
dev_langs:
- C++
helpviewer_keywords:
- floating-point functions, getting status word
- floating-point numbers, status word
- status87 function
- status word, getting floating point
- statusfp function
- _statusfp function
- _statusfp2 function
- statusfp2 function
- _status87 function
- floating-point functions
- status word
ms.assetid: 7ef963fa-b1fb-429d-94d6-fbf282ab7432
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 69a19aaa457ffc52c431a9ca1c3597a475a10994
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="status87-statusfp-statusfp2"></a>_status87, _statusfp, _statusfp2
Obtient le mot d’état de virgule flottante.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
unsigned int _status87( void );  
unsigned int _statusfp( void );  
void _statusfp2(unsigned int *px86, unsigned int *pSSE2)  
```  
  
#### <a name="parameters"></a>Paramètres  
 `px86`  
 Cette adresse est complétée avec le mot d’état de l’unité de virgule flottante x87.  
  
 `pSSE2`  
 Cette adresse est complétée avec le mot d’état de l’unité de virgule flottante SSE2.  
  
## <a name="return-value"></a>Valeur de retour  
 Pour `_status87` et `_statusfp`, les bits contenus dans la valeur retournée indiquent l’état de virgule flottante. Pour obtenir une définition des bits retournés par `_statusfp`, consultez le fichier Include FLOAT.H. Une part importante des fonctions de bibliothèque mathématique modifie le mot d’état de virgule flottante, avec des résultats imprévisibles. L’optimisation permet de réorganiser, combiner et éliminer les opérations en virgule flottante autour des appels à `_status87`, `_statusfp` et des fonctions associées. Utilisez l’option du compilateur [/Od (Désactiver (Déboage))](../../build/reference/od-disable-debug.md) ou la directive pragma [fenv_access](../../preprocessor/fenv-access.md) pour éviter les optimisations qui réorganisent les opérations en virgule flottante. Les valeurs de retour de `_clearfp` et `_statusfp`, de même que les paramètres de retour de `_statusfp2`, sont d’autant plus fiables que le nombre d’opérations en virgule flottante exécutées entre les états connus du mot d’état de virgule flottante est limité.  
  
## <a name="remarks"></a>Notes  
 La fonction `_statusfp` obtient le mot d’état de virgule flottante. Le mot d’état est une combinaison de l’état du processeur de virgule flottante et d’autres conditions détectées par le gestionnaire d’exceptions de virgule flottante, par exemple le dépassement de capacité positif et négatif de pile en virgule flottante. Les exceptions démasquées sont vérifiées avant que le contenu du mot d’état soit retourné. Cela signifie que l’appelant est informé des exceptions en attente. Sur les plateformes X86, `_statusfp` retourne une combinaison de l’état de virgule flottante x87 et SSE2. Sur les plateformes X64, l’état retourné repose sur l’état MXCSR de SSE. Sur les plateformes ARM, `_statusfp` retourne l’état du registre FPSCR.  
  
 `_statusfp` est une version portable indépendante de la plateforme de `_status87`. Elle est identique à `_status87` sur les plateformes Intel (x 86) et est aussi prise en charge par les plateformes x64 et ARM. Pour assurer la portabilité de votre code en virgule flottante vers toutes les architectures, utilisez `_statusfp`. Si vous ciblez uniquement les plateformes x86, vous pouvez utiliser `_status87` ou `_statusfp`.  
  
 Nous vous recommandons `_statusfp2` pour les puces (telles que Pentium IV) qui sont équipées de processeurs en virgule flottante x87 et SSE2. Pour `_statusfp2`, les adresses sont complétées avec le mot d’état de virgule flottante pour le processeur en virgule flottante x87 ou SSE2. Pour une puce qui prend en charge les processeurs en virgule flottante x87 et SSE2, l’indicateur EM_AMBIGUOUS prend la valeur 1 si `_statusfp` ou `_controlfp` est utilisé et que l’action était ambiguë, car il pourrait faire référence au mot d’état de virgule flottante x87 ou SSE2. La fonction `_statusfp2` n’est prise en charge que sur les plateformes x86.  
  
 Ces fonctions ne sont pas utiles pour [/clr (Compilation pour le Common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md) , car le common language runtime (CLR) prend uniquement en charge la précision en virgule flottante par défaut.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_status87`, `_statusfp`, `_statusfp2`|\<float.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_statusfp.c  
// Build by using: cl /W4 /Ox /nologo crt_statusfp.c  
// This program creates various floating-point errors and  
// then uses _statusfp to display messages that indicate these problems.  
  
#include <stdio.h>  
#include <float.h>  
#pragma fenv_access(on)  
  
double test( void )  
{  
   double a = 1e-40;  
   float b;  
   double c;  
  
   printf("Status = 0x%.8x - clear\n", _statusfp());  
  
   // Assignment into b is inexact & underflows:   
   b = (float)(a + 1e-40);  
   printf("Status = 0x%.8x - inexact, underflow\n", _statusfp());  
  
   // c is denormal:   
   c = b / 2.0;   
   printf("Status = 0x%.8x - inexact, underflow, denormal\n",   
            _statusfp());  
  
   // Clear floating point status:   
   _clearfp();  
   return c;  
}  
  
int main(void)  
{  
   return (int)test();  
}  
```  
  
```Output  
Status = 0x00000000 - clear  
Status = 0x00000003 - inexact, underflow  
Status = 0x00080003 - inexact, underflow, denormal  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [_clear87, _clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)
