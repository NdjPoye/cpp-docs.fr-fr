---
title: _control87, _controlfp, __control87_2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _control87
- _controlfp
- __control87_2
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
- _control87
- __control87_2
- control87
- _controlfp
- controlfp
- control87_2
- _control87_2
dev_langs:
- C++
helpviewer_keywords:
- floating-point numbers, control word
- _control87 function
- control87 function
- controlfp function
- _controlfp function
- __control87_2 function
- floating-point functions, setting control word
- floating-point functions
- EM_AMBIGUOUS
- control87_2 function
ms.assetid: 0d09729d-d9a0-43d6-864c-43ff25e7e0c5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d2405b569c7e7accb828ba7052a9ea9fae125f0a
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="control87-controlfp-control872"></a>_control87, _controlfp, __control87_2
Obtient et définit le mot de contrôle à virgule flottante. Une version plus sécurisée de `_controlfp` est disponible. Consultez [_controlfp_s](../../c-runtime-library/reference/controlfp-s.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
unsigned int _control87(   
   unsigned int new,  
   unsigned int mask   
);  
unsigned int _controlfp(   
   unsigned int new,  
   unsigned int mask   
);  
int __control87_2(  
   unsigned int new,  
   unsigned int mask,  
   unsigned int* x86_cw,  
   unsigned int* sse2_cw  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `new`  
 Nouvelles valeurs en bits du mot de contrôle.  
  
 `mask`  
 Masque des bits du nouveau mot de contrôle à définir.  
  
 `x86_cw`  
 Renseigné avec le mot de contrôle pour l’unité de virgule flottante x87. Passez la valeur 0 (`NULL`) pour définir le mot de contrôle SSE2 uniquement.  
  
 `sse2_cw`  
 Mot de contrôle pour l’unité de virgule flottante SSE. Passez la valeur 0 (`NULL`) pour définir le mot de contrôle x87 uniquement.  
  
## <a name="return-value"></a>Valeur de retour  
 Pour `_control87` et `_controlfp`, les bits contenus dans la valeur retournée indiquent l’état de contrôle à virgule flottante. Pour obtenir une définition complète des bits retournés par `_control87`, consultez FLOAT.H.  
  
 Pour `__control87_2`, la valeur de retour est 1, qui indique une réussite.  
  
## <a name="remarks"></a>Notes  
 La fonction `_control87` obtient et définit le mot de contrôle à virgule flottante. Le mot de contrôle à virgule flottante permet au programme de modifier les modes de précision, d’arrondi et d’infini dans le package mathématique à virgule flottante, selon la plateforme. Vous pouvez également utiliser `_control87` pour masquer ou démasquer les exceptions de virgule flottante. Si la valeur de `mask` est égale à 0, `_control87` obtient le mot de contrôle à virgule flottante. Si `mask` est différent de zéro, une nouvelle valeur pour le mot de contrôle est définie : pour tout bit activé (autrement dit, égal à 1) dans `mask`, le bit correspondant dans `new` est utilisé pour mettre à jour le mot de contrôle. En d’autres termes, `fpcntrl` `=` ((`fpcntrl` `& ~mask`) &#124; (`new & mask`)) où `fpcntrl` est le mot de contrôle à virgule flottante.  
  
> [!NOTE]
>  Par défaut, les bibliothèques d’exécution masquent toutes les exceptions de virgule flottante.  
  
 `_controlfp` est une version portable indépendante de la plateforme de `_control87`. Elle est presque identique à la fonction `_control87` sur les plateformes ARM, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] et Intel (x86). Si vous ciblez les plateformes ARM, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] ou x86, utilisez `_control87` ou `_controlfp`.  
  
 La différence entre `_control87` et `_controlfp` réside dans la manière dont elles traitent les valeurs DENORMAL. Pour les plateformes ARM, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] et Intel (x86), `_control87` peut définir et effacer le masque d’exception DENORMAL OPERAND. `_controlfp` ne modifie pas le masque d’exception DENORMAL OPERAND. Cet exemple illustre la différence :  
  
```  
_control87( _EM_INVALID, _MCW_EM );   
// DENORMAL is unmasked by this call  
_controlfp( _EM_INVALID, _MCW_EM );   
// DENORMAL exception mask remains unchanged  
```  
  
 Les valeurs possibles pour la constante du masque (`mask`) et les nouvelles valeurs de contrôle (`new`) sont indiquées dans le tableau Valeurs hexadécimales ci-après. Utilisez l’une des constantes portables répertoriées ci-dessous (`_MCW_EM`, `_EM_INVALID`, et ainsi de suite) en tant qu’arguments de ces fonctions, au lieu de fournir les valeurs hexadécimales explicitement.  
  
 Les plateformes dérivées d’Intel (x86) prennent en charge les valeurs d’entrée et de sortie DENORMAL dans le matériel. Le comportement x86 consiste à conserver les valeurs DENORMAL. Sur la plateforme ARM et les plateformes [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] qui prennent en charge SSE2, les opérandes et résultats DENORMAL peuvent être vidés ou définis sur zéro. Les fonctions `_controlfp` et `_control87` fournissent un masque pour modifier ce comportement. L’exemple suivant illustre l’utilisation de ce masque.  
  
```  
_controlfp(_DN_SAVE, _MCW_DN);     
// Denormal values preserved on ARM platforms and on x64 processors with  
// SSE2 support. NOP on x86 platforms.  
_controlfp(_DN_FLUSH, _MCW_DN);     
// Denormal values flushed to zero by hardware on ARM platforms   
// and x64 processors with SSE2 support. Ignored on other x86 platforms.  
```  
  
 Sur les plateformes ARM, les fonctions `_control87` et `_controlfp` s’appliquent au registre FPSCR. Sur les architectures [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], seul le mot de contrôle SSE2 stocké dans le registre MXCSR est affecté. Sur les plateformes Intel (x86), `_control87` et `_controlfp` affectent les mots de contrôle pour les unités x87 et SSE2, le cas échéant. La fonction `__control87_2` permet de contrôler les unités de virgule flottante x87 et SSE2 ensemble ou séparément. Si vous souhaitez affecter les deux unités, passez les adresses de deux entiers à `x86_cw` et `sse2_cw`. Si vous souhaitez uniquement affecter une unité, passez une adresse pour ce paramètre tout en passant la valeur 0 (NULL) pour l’autre. Si 0 est passé pour l’un de ces paramètres, la fonction n’a aucun effet sur cette unité de virgule flottante. Cette fonctionnalité peut être utile dans les cas où une partie du code utilise l’unité de virgule flottante x87 et une autre partie l’unité de virgule flottante SSE2. Si vous utilisez `__control87_2` dans une partie d’un programme et que vous définissez des valeurs différentes pour les mots de contrôle à virgule flottante, puis que vous utilisez `_control87` ou `_controlfp` pour manipuler le mot de contrôle, `_control87` et `_controlfp` peuvent être incapables de renvoyer un mot de contrôle unique pour représenter l’état des deux unités de virgule flottante. Dans ce cas, ces fonctions définissent l’indicateur `EM_AMBIGUOUS` dans la valeur entière retournée pour indiquer qu’il existe une incohérence entre les deux mots de contrôle. Il s’agit d’un message d’avertissement selon lequel le mot de contrôle retourné peut ne pas représenter l’état des deux mots de contrôle à virgule flottante avec précision.  
  
 Sur les architectures ARM et [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], changer le mode d’infini ou la précision à virgule flottante n’est pas pris en charge. Si le masque de contrôle de la précision est utilisé sur la plateforme [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], la fonction génère une assertion et le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  
  
> [!NOTE]
>  `__control87_2` n’est pas prise en charge sur les architectures ARM ou [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]. Si vous utilisez `__control87_2` et compilez votre programme pour les architectures ARM ou [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], le compilateur génère une erreur.  
  
 Ces fonctions sont ignorées lorsque vous utilisez [/clr (Compilation pour le Common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md) de compilation parce que le common language runtime (CLR) prend uniquement en charge la précision en virgule flottante par défaut.  
  
 **Valeurs hexadécimales**  
  
 Concernant le masque `_MCW_EM`, désactiver ce dernier définit l’exception, ce qui permet l’exception matérielle, tandis que le définir masque l’exception. Si un `_EM_UNDERFLOW` ou `_EM_OVERFLOW` se produit, aucune exception de matériel n’est levée tant que l’instruction à virgule flottante suivante n’est pas exécutée. Pour générer une exception matérielle immédiatement après `_EM_UNDERFLOW` ou `_EM_OVERFLOW`, appelez l’instruction MASM `FWAIT`.  
  
|Masque|Valeur hexadécimale|Constante|Valeur hexadécimale|  
|----------|---------------|--------------|---------------|  
|`_MCW_DN` (contrôle de la dénormalisation)|0x03000000|`_DN_SAVE`<br /><br /> `_DN_FLUSH`|0x00000000<br /><br /> 0x01000000|  
|`_MCW_EM` (masque d’exception d’interruption)|0x0008001F|`_EM_INVALID`<br /><br /> `_EM_DENORMAL`<br /><br /> `_EM_ZERODIVIDE`<br /><br /> `_EM_OVERFLOW`<br /><br /> `_EM_UNDERFLOW`<br /><br /> `_EM_INEXACT`|0x00000010<br /><br /> 0x00080000<br /><br /> 0x00000008<br /><br /> 0x00000004<br /><br /> 0x00000002<br /><br /> 0x00000001|  
|`_MCW_IC` (Contrôle de l’infini)<br /><br /> (Non pris en charge sur les plateformes ARM ou [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)].)|0x00040000|`_IC_AFFINE`<br /><br /> `_IC_PROJECTIVE`|0x00040000<br /><br /> 0x00000000|  
|`_MCW_RC` (Contrôle de l’arrondi)|0x00000300|`_RC_CHOP`<br /><br /> `_RC_UP`<br /><br /> `_RC_DOWN`<br /><br /> `_RC_NEAR`|0x00000300<br /><br /> 0x00000200<br /><br /> 0x00000100<br /><br /> 0x00000000|  
|`_MCW_PC` (Contrôle de la précision)<br /><br /> (Non pris en charge sur les plateformes ARM ou [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)].)|0x00030000|`_PC_24` (24 bits)<br /><br /> `_PC_53` (53 bits)<br /><br /> `_PC_64` (64 bits)|0x00020000<br /><br /> 0x00010000<br /><br /> 0x00000000|  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_control87`, `_controlfp`, `_control87_2`|\<float.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
  
```C  
// crt_cntrl87.c  
// processor: x86  
// This program uses __control87_2 to output the x87 control   
// word, set the precision to 24 bits, and reset the status to   
// the default.  
  
#include <stdio.h>  
#include <float.h>  
#pragma fenv_access (on)  
  
int main( void )  
{  
    double a = 0.1;  
    unsigned int control_word_x87;  
  
    // Show original x87 control word and do calculation.  
    control_word_x87 = __control87_2(0, 0,  
                                     &control_word_x87, 0);  
    printf( "Original: 0x%.4x\n", control_word_x87 );  
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );  
  
    // Set precision to 24 bits and recalculate.  
    control_word_x87 = __control87_2(_PC_24, MCW_PC,  
                                     &control_word_x87, 0);  
    printf( "24-bit:   0x%.4x\n", control_word_x87 );  
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );  
  
    // Restore default precision-control bits and recalculate.  
    control_word_x87 = __control87_2( _CW_DEFAULT, MCW_PC,   
                                     &control_word_x87, 0 );  
    printf( "Default:  0x%.4x\n", control_word_x87 );  
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );  
}  
```  
  
```Output  
Original: 0x0001  
0.1 * 0.1 = 1.000000000000000e-002  
24-bit:   0x0001  
0.1 * 0.1 = 9.999999776482582e-003  
Default:  0x0001  
0.1 * 0.1 = 1.000000000000000e-002  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [_clear87, _clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [_status87, _statusfp, _statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)   
 [_controlfp_s](../../c-runtime-library/reference/controlfp-s.md)