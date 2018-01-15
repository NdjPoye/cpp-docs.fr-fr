---
title: _controlfp_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _controlfp_s
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
- controlfp_s
- _controlfp_s
dev_langs: C++
helpviewer_keywords:
- floating-point numbers, control word
- controlfp_s function
- floating-point functions, setting control word
- EM_AMBIGUOUS
- _controlfp_s function
ms.assetid: a51fc3f6-ab13-41f0-b227-6bf02d98e987
caps.latest.revision: "28"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a8c8f651e04a1d68cd27f8321d6a30250c0e6ce1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="controlfps"></a>_controlfp_s
Obtient et définit le mot de contrôle à virgule flottante. Cette version de [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md) est assortie des améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
errno_t _controlfp_s(  
    unsigned int *currentControl,  
    unsigned int newControl,  
    unsigned int mask  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `currentControl`  
 Valeur en bits du mot de contrôle actuelle.  
  
 `newControl`  
 Nouvelles valeurs en bits du mot de contrôle.  
  
 `mask`  
 Masque des bits du nouveau mot de contrôle à définir.  
  
## <a name="return-value"></a>Valeur de retour  
 Zéro en cas de réussite, ou un code d’erreur de valeur `errno`.  
  
## <a name="remarks"></a>Notes  
 La fonction `_controlfp_s` est une version de `_control87` indépendante de la plateforme et plus sûre, qui obtient le mot de contrôle à virgule flottante dans l’adresse stockée dans `currentControl` et le définit à l’aide de `newControl`. Les bits contenus dans les valeurs indiquent l’état de contrôle à virgule flottante. L’état de contrôle à virgule flottante permet au programme de modifier les modes de précision, d’arrondi et d’infini dans le package mathématique à virgule flottante, selon la plateforme. Vous pouvez également utiliser `_controlfp_s` pour masquer ou démasquer les exceptions de virgule flottante.  
  
 Si la valeur de `mask` est égale à 0, `_controlfp_s` obtient le mot de contrôle à virgule flottante et stocke la valeur récupérée dans `currentControl`.  
  
 Si `mask` est différent de zéro, une nouvelle valeur pour le mot de contrôle est définie : pour tout bit défini (autrement dit, égal à 1) dans `mask`, le bit correspondant dans `new` est utilisé pour mettre à jour le mot de contrôle. En d’autres termes, `fpcntrl` `=` ((`fpcntrl` `& ~mask`) &#124; (`new & mask`)) où `fpcntrl` est le mot de contrôle à virgule flottante. Dans ce scénario, `currentControl` est défini sur la valeur une fois la modification effectuée ; il ne s’agit pas de l’ancienne valeur de bit du mot de contrôle.  
  
> [!NOTE]
>  Par défaut, les bibliothèques d’exécution masquent toutes les exceptions de virgule flottante.  
  
 `_controlfp_s` est presque identique à la fonction `_control87` sur les plateformes ARM, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] et Intel (x86). Si vous ciblez les plateformes ARM, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] ou x86, vous pouvez utiliser `_control87` ou `_controlfp_s`.  
  
 La différence entre `_control87` et `_controlfp_s` réside dans la manière dont elles traitent les valeurs `DENORMAL`. Pour les plateformes ARM, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] et Intel (x86), `_control87` peut définir et effacer le masque d’exception DENORMAL OPERAND. `_controlfp_s` ne modifie pas le masque d’exception DENORMAL OPERAND. Cet exemple illustre la différence :  
  
```C  
_control87( _EM_INVALID, _MCW_EM );   
// DENORMAL is unmasked by this call.  
unsigned int current_word = 0;  
_controlfp_s( &current_word, _EM_INVALID, _MCW_EM );   
// DENORMAL exception mask remains unchanged.  
```  
  
 Les valeurs possibles pour la constante du masque (`mask`) et les nouvelles valeurs de contrôle (`newControl`) sont indiquées dans le tableau Valeurs hexadécimales ci-après. Utilisez l’une des constantes portables répertoriées ci-dessous (`_MCW_EM`, `_EM_INVALID`, et ainsi de suite) en tant qu’arguments de ces fonctions, au lieu de fournir les valeurs hexadécimales explicitement.  
  
 Les plateformes dérivées d’Intel (x86) prennent en charge les valeurs d’entrée et de sortie DENORMAL dans le matériel. Le comportement x86 consiste à conserver les valeurs DENORMAL. Sur la plateforme ARM et les plateformes [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] qui prennent en charge SSE2, les opérandes et résultats DENORMAL peuvent être vidés ou définis sur zéro. Les fonctions `_controlfp_s`, `_controlfp` et `_control87` fournissent un masque pour modifier ce comportement. L’exemple suivant illustre l’utilisation de ce masque :  
  
```C  
unsigned int current_word = 0;  
_controlfp_s(&current_word, _DN_SAVE, _MCW_DN);     
// Denormal values preserved on ARM platforms and on x64 processors with  
// SSE2 support. NOP on x86 platforms.  
_controlfp_s(&current_word, _DN_FLUSH, _MCW_DN);     
// Denormal values flushed to zero by hardware on ARM platforms   
// and x64 processors with SSE2 support. Ignored on other x86 platforms.  
```  
  
 Sur les plateformes ARM, la fonction `_controlfp_s` s’applique au registre FPSCR. Sur les architectures [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], seul le mot de contrôle SSE2 stocké dans le registre MXCSR est affecté. Sur les plateformes Intel (x86), `_controlfp_s` affecte les mots de contrôle pour les unités x87 et SSE2, le cas échéant. Il est possible que deux mots de contrôle soient incohérents entre eux (en raison d’un appel précédent à [__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md), par exemple) ; dans ce cas, `_controlfp_s` définit l’indicateur `EM_AMBIGUOUS` dans `currentControl`. Il s’agit d’un message d’avertissement selon lequel le mot de contrôle retourné peut ne pas représenter l’état des deux mots de contrôle à virgule flottante avec précision.  
  
 Sur les architectures ARM et [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], changer le mode d’infini ou la précision à virgule flottante n’est pas pris en charge. Si le masque de contrôle de la précision est utilisé sur la plateforme [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], la fonction génère une assertion et le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  
  
 Si le masque n’est défini correctement, cette fonction génère une exception de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, cette fonction retourne `EINVAL` et affecte la valeur `errno` à `EINVAL`.  
  
 Cette fonction est ignorée lorsque vous utilisez [/clr (Compilation pour le Common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md) de compilation parce que le common language runtime (CLR) prend uniquement en charge la précision en virgule flottante par défaut.  
  
### <a name="mask-constants-and-values"></a>Masque les constantes et valeurs  
  
 Concernant le masque `_MCW_EM`, désactiver ce dernier définit l’exception, ce qui permet l’exception matérielle, tandis que le définir masque l’exception. Si un `_EM_UNDERFLOW` ou `_EM_OVERFLOW` se produit, aucune exception de matériel n’est levée tant que l’instruction à virgule flottante suivante n’est pas exécutée. Pour générer une exception matérielle immédiatement après `_EM_UNDERFLOW` ou `_EM_OVERFLOW`, appelez l’instruction MASM FWAIT.  
  
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
|`_controlfp_s`|\<float.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="example"></a>Exemple  
  
```C  
// crt_contrlfp_s.c  
// processor: x86  
// This program uses _controlfp_s to output the FP control   
// word, set the precision to 24 bits, and reset the status to   
// the default.  
  
#include <stdio.h>  
#include <float.h>  
#pragma fenv_access (on)  
  
int main( void )  
{  
    double a = 0.1;  
    unsigned int control_word;  
    int err;  
  
    // Show original FP control word and do calculation.  
    err = _controlfp_s(&control_word, 0, 0);  
    if ( err ) /* handle error here */;  
  
    printf( "Original: 0x%.4x\n", control_word );  
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );  
  
    // Set precision to 24 bits and recalculate.  
    err = _controlfp_s(&control_word, _PC_24, MCW_PC);  
    if ( err ) /* handle error here */;  
  
    printf( "24-bit:   0x%.4x\n", control_word );  
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );  
  
    // Restore default precision-control bits and recalculate.  
    err = _controlfp_s(&control_word, _CW_DEFAULT, MCW_PC);  
    if ( err ) /* handle error here */;  
  
    printf( "Default:  0x%.4x\n", control_word );  
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );  
}  
```  
  
```Output  
Original: 0x9001f  
0.1 * 0.1 = 1.000000000000000e-002  
24-bit:   0xa001f  
0.1 * 0.1 = 9.999999776482582e-003  
Default:  0x9001f  
0.1 * 0.1 = 1.000000000000000e-002  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [_clear87, _clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [_status87, _statusfp, _statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)   
 [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)