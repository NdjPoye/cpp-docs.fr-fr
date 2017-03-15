---
title: _CrtSetDbgFlag | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtSetDbgFlag
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
apitype: DLLExport
f1_keywords:
- _CRTDBG_REPORT_FLAG
- _CRTDBG_CHECK_EVERY_16_DF
- _CRTDBG_CHECK_DEFAULT_DF
- CRTDBG_CHECK_DEFAULT_DF
- CRTDBG_CHECK_EVERY_128_DF
- CRTDBG_CHECK_EVERY_1024_DF
- _CRTDBG_CHECK_EVERY_128_DF
- CrtSetDbgFlag
- CRTDBG_CHECK_EVERY_16_DF
- _CRTDBG_CHECK_EVERY_1024_DF
- _CrtSetDbgFlag
- CRTDBG_REPORT_FLAG
dev_langs:
- C++
helpviewer_keywords:
- _CRTDBG_CHECK_EVERY_16_DF macro
- CRTDBG_CHECK_EVERY_16_DF macro
- _CRTDBG_CHECK_ALWAYS_DF macro
- _CRTDBG_CHECK_DEFAULT_DF macro
- CRTDBG_ALLOC_MEM_DF macro
- CRTDBG_CHECK_ALWAYS_DF macro
- _CRTDBG_ALLOC_MEM_DF macro
- _CRTDBG_REPORT_FLAG macro
- _CRTDBG_CHECK_EVERY_128_DF macro
- CRTDBG_REPORT_FLAG macro
- _CRTDBG_CHECK_EVERY_1024_DF macro
- CRTDBG_CHECK_DEFAULT_DF macro
- CRTDBG_CHECK_EVERY_1024_DF macro
- _CrtSetDbgFlag function
- CrtSetDbgFlag function
- _CRTDBG_DELAY_FREE_MEM_DF macro
- CRTDBG_CHECK_EVERY_128_DF macro
- CRTDBG_DELAY_FREE_MEM_DF macro
- CRTDBG_CHECK_CRT_DF macro
- _CRTDBG_CHECK_CRT_DF macro
ms.assetid: b5657ffb-6178-4cbf-9886-1af904ede94c
caps.latest.revision: 19
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: d6ed7ff3e28028e3e4b46055e51c32037b0b5a15
ms.lasthandoff: 02/24/2017

---
# <a name="crtsetdbgflag"></a>_CrtSetDbgFlag
Récupère ou modifie l’état de l’indicateur **_crtDbgFlag** pour contrôler le comportement d’allocation du gestionnaire de tas de débogage (version de débogage uniquement).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      int _CrtSetDbgFlag(   
   int newFlag   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `newFlag`  
 Nouvel état pour **_crtDbgFlag**.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne l’état précédent de **_crtDbgFlag**.  
  
## <a name="remarks"></a>Notes  
 La fonction `_CrtSetDbgFlag` permet à l’application de contrôler comment le gestionnaire de tas de débogage suit les allocations de mémoire en modifiant les champs de bits de l’indicateur **_crtDbgFlag**. En définissant les bits (activation), l'application peut indiquer au gestionnaire de tas de débogage d'exécuter des opérations spécifiques de débogage, notamment la recherche de fuites de mémoire quand l'application s'arrête et la création de rapports si certaines sont détectées, la simulation de conditions de mémoire insuffisante en spécifiant que les blocs de mémoire libérés doivent rester dans la liste liée du tas, et la vérification de l'intégrité du tas en inspectant chaque bloc de mémoire lors de chaque demande d'allocation. Quand [_DEBUG](../../c-runtime-library/debug.md) n’est pas défini, les appels à `_CrtSetDbgFlag` sont supprimés durant le prétraitement.  
  
 Le tableau suivant répertorie les champs de bits pour **_crtDbgFlag** et décrit leur comportement. Comme la définition des bits aboutit à une augmentation de la sortie des diagnostics et à une réduction de la vitesse d'exécution du programme, ces bits ne sont pas définis (désactivés) par défaut. Pour plus d’informations sur ces champs de bits, voir [Fonctions de création de rapports sur l’état du tas](/visualstudio/debugger/crt-debug-heap-details).  
  
|Champ de bits|Valeur|Description|  
|---------------|-------------|-----------------|  
|**_CRTDBG_ALLOC_MEM_DF**|ON|ON : permet les allocations de tas de débogage et l'utilisation des identificateurs de type de bloc de mémoire, tels que `_CLIENT_BLOCK`. OFF : ajoute les nouvelles allocations à la liste liée du tas, mais affecte au type de bloc la valeur **_IGNORE_BLOCK**.<br /><br /> Peuvent aussi être combinés avec n'importe quelle macro de contrôle de fréquence sur le tas.|  
|**_CRTDBG_CHECK_ALWAYS_DF**|OFF|ON : appelle [_CrtCheckMemory](../../c-runtime-library/reference/crtcheckmemory.md) à chaque demande d’allocation et de désallocation. OFF : `_CrtCheckMemory` doit être appelé explicitement.<br /><br /> Les macros de contrôle de fréquence sur le tas n'ont aucun effet quand cet indicateur est défini.|  
|`_CRTDBG_CHECK_CRT_DF`|OFF|ON : inclut les types `_CRT_BLOCK` dans les opérations de détection des fuites et de différence d'état de mémoire. OFF : la mémoire utilisée en interne par la bibliothèque Runtime est ignorée par ces opérations.<br /><br /> Peuvent aussi être combinés avec n'importe quelle macro de contrôle de fréquence sur le tas.|  
|**_CRTDBG_DELAY_FREE_MEM_DF**|OFF|ON : conserve les blocs de mémoire libérés dans la liste liée du tas, leur assigne le type **_FREE_BLOCK** et les remplit avec la valeur d’octet 0xDD. OFF : ne conserve pas les blocs libérés dans la liste liée du tas.<br /><br /> Peuvent aussi être combinés avec n'importe quelle macro de contrôle de fréquence sur le tas.|  
|`_CRTDBG_LEAK_CHECK_DF`|OFF|ON : exécute la recherche automatique de fuites à la sortie du programme via un appel à [_CrtDumpMemoryLeaks](../../c-runtime-library/reference/crtdumpmemoryleaks.md) et génère un rapport d’erreurs si l’application n’a pas pu libérer toute la mémoire qu’elle avait allouée. OFF : n'exécute pas automatiquement la recherche de fuites à la sortie du programme.<br /><br /> Peuvent aussi être combinés avec n'importe quelle macro de contrôle de fréquence sur le tas.|  
  
 **Macros de contrôle de fréquence sur le tas**  
  
 Vous pouvez spécifier la fréquence à laquelle la bibliothèque Runtime C effectue la validation du tas de débogage (`_CrtCheckMemory`) en fonction du nombre d’appels à `malloc`, `realloc`, **free** et `_msize`.  
  
 `_CrtSetDbgFlag` inspecte ensuite les 16 bits supérieurs du paramètre `newFlag` pour une valeur. La valeur spécifiée est le nombre d’appels à `malloc`, `realloc`, **free** et `_msize` entre les appels à `_CrtCheckMemory`. Quatre macros prédéfinies sont fournies à cet effet.  
  
|Macro|Nombre d'appels à malloc, realloc, free et _msize entre les appels à _CrtCheckMemory|  
|-----------|------------------------------------------------------------------------------------------|  
|_CRTDBG_CHECK_EVERY_16_DF|16|  
|_CRTDBG_CHECK_EVERY_128_DF|128|  
|_CRTDBG_CHECK_EVERY_1024_DF|1024|  
|_CRTDBG_CHECK_DEFAULT_DF|0 (par défaut, aucun contrôle du tas)|  
  
 Par défaut, `_CrtCheckMemory` est appelé une fois toutes les 1 024 fois que vous appelez `malloc`, `realloc`, **free** et `_msize`.  
  
 Par exemple, vous pouvez spécifier un contrôle du tas toutes les 16 opérations sur `malloc`, `realloc`, **free** et `_msize` avec le code suivant :  
  
```  
#include <crtdbg.h>  
int main( )  
{  
int tmp;  
  
// Get the current bits  
tmp = _CrtSetDbgFlag(_CRTDBG_REPORT_FLAG);  
  
// Clear the upper 16 bits and OR in the desired freqency  
tmp = (tmp & 0x0000FFFF) | _CRTDBG_CHECK_EVERY_16_DF;  
  
// Set the new bits  
_CrtSetDbgFlag(tmp);  
}  
```  
  
 Les 16 bits supérieurs du paramètre `newFlag` sont ignorés quand _CRTDBG_CHECK_ALWAYS_DF est spécifié. Dans ce cas, `_CrtCheckMemory` est appelé chaque fois que vous appelez `malloc`, `realloc`, **free** et `_msize`.  
  
 `newFlag` est le nouvel état à appliquer à **_crtDbgFlag** et est une combinaison des valeurs pour chacun des champs de bits.  
  
### <a name="to-change-one-or-more-of-these-bit-fields-and-create-a-new-state-for-the-flag"></a>Pour changer un ou plusieurs de ces champs de bits et créer un état pour l'indicateur  
  
1.  Appelez `_CrtSetDbgFlag` en ayant `newFlag` égal à `_CRTDBG_REPORT_FLAG` pour obtenir l’état actuel de **_crtDbgFlag** et stockez la valeur retournée dans une variable temporaire.  
  
2.  Activez les bits par une opération `OR` sur la variable temporaire avec les masques de bits correspondants (représentés dans le code de l'application par des constantes manifestes).  
  
3.  Désactivez les autres bits par une opération **AND** sur la variable avec une opération **NOT** au niveau du bit des masques de bits appropriés.  
  
4.  Appelez `_CrtSetDbgFlag` en ayant `newFlag` égal à la valeur stockée dans la variable temporaire pour définir le nouvel état de **_crtDbgFlag**.  
  
 Le code suivant montre comment simuler des conditions de mémoire insuffisante en conservant les blocs de mémoire libérés dans la liste liée du tas et empêcher `_CrtCheckMemory` d'être appelé à chaque demande d'allocation :  
  
```  
// Get the current state of the flag  
// and store it in a temporary variable  
int tmpFlag = _CrtSetDbgFlag( _CRTDBG_REPORT_FLAG );  
  
// Turn On (OR) - Keep freed memory blocks in the  
// heap's linked list and mark them as freed  
tmpFlag |= _CRTDBG_DELAY_FREE_MEM_DF;  
  
// Turn Off (AND) - prevent _CrtCheckMemory from  
// being called at every allocation request  
tmpFlag &= ~_CRTDBG_CHECK_ALWAYS_DF;  
  
// Set the new state for the flag  
_CrtSetDbgFlag( tmpFlag );  
```  
  
 Pour obtenir une vue d’ensemble de la gestion de la mémoire et du tas de débogage, consultez [Détails du tas de débogage CRT](/visualstudio/debugger/crt-debug-heap-details).  
  
 Pour désactiver un indicateur avec la fonction `_CrtSetDbgFlag`, vous devez procéder à une opération **AND** sur la variable avec une opération **NOT** au niveau du bit du masque de bits.  
  
 Si `newFlag` n’est pas une valeur valide, cette fonction appelle le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, cette fonction affecte la valeur `errno` à `EINVAL` et retourne l'état précédent de `_crtDbgFlag`.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_CrtSetDbgFlag`|\<crtdbg.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Uniquement les versions de débogage des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_crtsetdflag.c  
// compile with: /c -D_DEBUG /MTd -Od -Zi -W3 /link -verbose:lib /debug  
/*  
 * This program concentrates on allocating and freeing memory  
 * blocks to test the functionality of the _crtDbgFlag flag..  
 */  
  
#include <string.h>  
#include <malloc.h>  
#include <crtdbg.h>  
  
int main( )  
{  
        char *p1, *p2;  
        int tmpDbgFlag;  
  
        _CrtSetReportMode( _CRT_ERROR, _CRTDBG_MODE_FILE );  
        _CrtSetReportFile( _CRT_ERROR, _CRTDBG_FILE_STDERR );  
        /*  
         * Set the debug-heap flag to keep freed blocks in the  
         * heap's linked list - This will allow us to catch any  
         * inadvertent use of freed memory  
         */  
        tmpDbgFlag = _CrtSetDbgFlag(_CRTDBG_REPORT_FLAG);  
        tmpDbgFlag |= _CRTDBG_DELAY_FREE_MEM_DF;  
        tmpDbgFlag |= _CRTDBG_LEAK_CHECK_DF;  
        _CrtSetDbgFlag(tmpDbgFlag);  
  
        /*  
         * Allocate 2 memory blocks and store a string in each  
         */  
        p1 = malloc( 34 );  
        p2 = malloc( 38 );  
        strcpy_s( p1, 34, "p1 points to a Normal allocation block" );  
        strcpy_s( p2, 38, "p2 points to a Client allocation block" );  
  
        /*  
         * Free both memory blocks  
         */  
        free( p2 );  
        free( p1 );  
  
        /*  
         * Set the debug-heap flag to no longer keep freed blocks in the  
         * heap's linked list and turn on Debug type allocations (CLIENT)  
         */  
        tmpDbgFlag = _CrtSetDbgFlag(_CRTDBG_REPORT_FLAG);  
        tmpDbgFlag |= _CRTDBG_ALLOC_MEM_DF;  
        tmpDbgFlag &= ~_CRTDBG_DELAY_FREE_MEM_DF;  
        _CrtSetDbgFlag(tmpDbgFlag);  
  
        /*  
         * Explicitly call _malloc_dbg to obtain the filename and   
         * line number of our allocation request and also so we can   
         * allocate CLIENT type blocks specifically for tracking  
         */  
        p1 = _malloc_dbg( 40, _NORMAL_BLOCK, __FILE__, __LINE__ );  
        p2 = _malloc_dbg( 40, _CLIENT_BLOCK, __FILE__, __LINE__ );  
        strcpy_s( p1, 40, "p1 points to a Normal allocation block" );  
        strcpy_s( p2, 40, "p2 points to a Client allocation block" );  
  
        /*  
         * _free_dbg must be called to free the CLIENT block  
         */  
        _free_dbg( p2, _CLIENT_BLOCK );  
        free( p1 );  
  
        /*  
         * Allocate p1 again and then exit - this will leave unfreed  
         * memory on the heap  
         */  
        p1 = malloc( 10 );  
}  
```  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)   
 [_CrtCheckMemory](../../c-runtime-library/reference/crtcheckmemory.md)
