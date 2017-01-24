---
title: "_controlfp_s | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_controlfp_s"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "controlfp_s"
  - "_controlfp_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_controlfp_s (fonction)"
  - "controlfp_s (fonction)"
  - "EM_AMBIGUOUS"
  - "fonctions en virgule flottante, définir un mot de commande"
  - "chiffres à virgule flottante, mot de commande"
ms.assetid: a51fc3f6-ab13-41f0-b227-6bf02d98e987
caps.latest.revision: 28
caps.handback.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _controlfp_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient et définit le mot de contrôle à virgule flottante.  Cette version de [\_control87, \_controlfp, \_\_control87\_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md) présente des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
errno_t _controlfp_s(  
    unsigned int *currentControl,  
    unsigned int newControl,  
    unsigned int mask  
);  
```  
  
#### Paramètres  
 `currentControl`  
 La valeur binaire actuelle du mot de contrôle.  
  
 `newControl`  
 Nouvelles valeurs des bits du mot de contrôle.  
  
 `mask`  
 Masque pour de nouveaux bits du mot de contrôle à définir.  
  
## Valeur de retour  
 Zéro si l'opération a réussi ; ou un code de valeur `errno`.  
  
## Notes  
 La fonction `_controlfp_s` est une version plus sécurisée et indépendante de la plateforme de `_control87`, qui entre le mot de contrôle à virgule flottante dans l'adresse stockée dans `currentControl` et le définit à l'aide de `newControl`.  Les bits dans les valeurs indiquent l'état du contrôle à virgule flottante.  L'état du contrôle à virgule flottante permet au programme de modifier la précision, l'arrondi, et les modes infinis dans le package mathématiqus à virgule flottante, selon la plateforme.  Utilisez également `_controlfp_s` pour masquer ou démasquer des exceptions de virgule flottante.  
  
 Si la valeur de `mask` est égale à 0, `_controlfp_s` obtient le mot de contrôle à virgule flottante et stocke la valeur récupérée dans `currentControl`.  
  
 Si `mask` est différent de zéro, une nouvelle valeur pour le mot de contrôle est définie : Pour tout bit qui est défini \(autrement dit, égal à 1\) dans `mask`, le bit correspondant dans `new` est utilisé pour mettre à jour le mot de contrôle.  En d'autres termes, `fpcntrl` `=` \(\(`fpcntrl` `& ~mask`\) &#124; \(`new & mask`\)\) où `fpcntrl` correspond au mot de contrôle à virgule flottante.  Dans ce scénario, `currentControl` est affecté à la valeur après que la modification est terminée; ce n'est pas la valeur binaire ancienne du mot de contrôle.  
  
> [!NOTE]
>  Par défaut, les bibliothèques runtime masquent toutes les exceptions de virgule flottante.  
  
 `_controlfp_s` est presque identique à la fonction `_control87` sur Intel \(x86\), [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], et sur les plateformes ARM.  Si vous ciblez x86, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], ou les plateformes ARM, utilisez `_control87` ou `_controlfp_s`.  
  
 La différence entre `_control87` et `_controlfp_s` réside dans la façon dont ils traitent des valeurs `DENORMAL`.  Pour les plateformes Intel \(x86\), [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], et ARM, `_control87` peut définir et effacer le masque d'exception d'opérandes dénormalisées.  `_controlfp_s` ne modifie pas le masque d'exception d'opérande dénormalisée.  Cet exemple illustre la différence :  
  
```  
_control87( _EM_INVALID, _MCW_EM );   
// DENORMAL is unmasked by this call.  
unsigned int current_word = 0;  
_controlfp_s( &current_word, _EM_INVALID, _MCW_EM );   
// DENORMAL exception mask remains unchanged.  
```  
  
 Les valeurs possibles pour la constante de masque \(`mask`\) et les nouvelles valeurs de contrôle \(`newControl`\) s'affichent dans le tableau de valeurs hexadécimales suivant.  Utilisez les constantes portables répertoriées ci\-dessous \(`_MCW_EM`, `_EM_INVALID`, etc.\) comme arguments à ces fonctions, plutôt qu'en fournissant des valeurs hexadécimales explicitement.  
  
 Les plateformes dérivées d'Intel \(x86\) prennent en charge les valeurs d'entrée et de sortie dénormalisées au niveau matériel.  Le comportement de x86 est de conserver les valeurs dénormalisées.  La plateforme ARM et les plateformes [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] qui prennent en charge SSE2 autorisent des opérandes et des résultats dénormalisés à être nettoyés ou à être forcés à zéro.  Les fonctions `_controlfp_s`, `_controlfp`, et `_control87` fournissent un masque pour modifier ce comportement.  L'exemple suivant illustre l'utilisation de ce mask :  
  
```  
unsigned int current_word = 0;  
_controlfp_s(&current_word, _DN_SAVE, _MCW_DN);     
// Denormal values preserved on ARM platforms and on x64 processors with  
// SSE2 support. NOP on x86 platforms.  
_controlfp_s(&current_word, _DN_FLUSH, _MCW_DN);     
// Denormal values flushed to zero by hardware on ARM platforms   
// and x64 processors with SSE2 support. Ignored on other x86 platforms.  
```  
  
 Sur les plateformes ARM, la fonction `_controlfp_s` s'applique au registre FPSCR.  Sur les architectures [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], seul le mot de contrôle SSE2 qui est stocké dans le registre de MXCSR est affecté.  Sur les plateformes Intel \(x86\), `_controlfp_s` affecte les mots de contrôle pour le x87 et le SSE2, le cas échéant.  Il est possible que les deux mots de contrôle soient incohérent entre eux \(en raison d'un appel précédent à [\_\_control87\_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md), par exemple\) ; si une incohérence entre les deux mots de contrôle, `_controlfp_s` définit l'indicateur `EM_AMBIGUOUS` dans `currentControl`.  Ceci avertit que le mot de contrôle retourné peut ne pas représenter exactement l'état des deux mots de commande à virgule flottante.  
  
 Sur les architectures ARM et [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], modifier le mode infini ou la précision de la virgule flottante n'est pas pris en charge.  Si le masque de contrôle de précision est utilisé sur la plateforme [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], la fonction lève une assertion et le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  
  
 Si le masque n'est pas correctement défini, cette fonction génère une exception de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction renvoie `EINVAL` et définit `errno` avec la valeur `EINVAL`.  
  
 Cette fonction est ignorée lorsque vous utilisez [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md) ou **\/clr:pure** pour compiler car le Common Langage Runtime \(CLR\) ne prend en charge que la précision de virgule flottante par défaut.  
  
 **Valeurs hexadécimale**  
  
 Pour le masque `_MCW_EM`, le nettoyage du masque définit l'exception, ce qui permet l'exception matérielle ; la définition du masque cache l'exception.  Si un `_EM_UNDERFLOW` ou un `_EM_OVERFLOW` se produit, aucune exception matérielle n'est levée jusqu'à ce que l'instruction à virgule flottante suivante soit exécutée.  Pour générer une exception matérielle immédiatement après `_EM_UNDERFLOW` ou `_EM_OVERFLOW`, appelez l'instruction MASM .  
  
|Masque|Valeur hexadécimale|Constante|Valeur hexadécimale|  
|------------|-------------------------|---------------|-------------------------|  
|`_MCW_DN` \(contrôle dénormalisé\)|0x03000000|`_DN_SAVE`<br /><br /> `_DN_FLUSH`|0x00000000<br /><br /> 0x01000000|  
|`_MCW_EM` \(masque d'exception d'interruption\)|0x0008001F|`_EM_INVALID`<br /><br /> `_EM_DENORMAL`<br /><br /> `_EM_ZERODIVIDE`<br /><br /> `_EM_OVERFLOW`<br /><br /> `_EM_UNDERFLOW`<br /><br /> `_EM_INEXACT`|0x00000010<br /><br /> 0x00080000<br /><br /> 0x00000008<br /><br /> 0x00000004<br /><br /> 0x00000002<br /><br /> 0x00000001|  
|`_MCW_IC` \(contrôle Infini\)<br /><br /> \(Non pris en charge sur les plateformes ARM ou [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] .\)|0x00040000|`_IC_AFFINE`<br /><br /> `_IC_PROJECTIVE`|0x00040000<br /><br /> 0x00000000|  
|`_MCW_RC` \(contrôle d'arrondi\)|0x00000300|`_RC_CHOP`<br /><br /> `_RC_UP`<br /><br /> `_RC_DOWN`<br /><br /> `_RC_NEAR`|0x00000300<br /><br /> 0x00000200<br /><br /> 0x00000100<br /><br /> 0x00000000|  
|`_MCW_PC` \(contrôle de précision\)<br /><br /> \(Non pris en charge sur les plateformes ARM ou [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] .\)|0x00030000|`_PC_24` \(24 bits\)<br /><br /> `_PC_53` \(53 bits\)<br /><br /> `_PC_64` \(64 bits\)|0x00020000<br /><br /> 0x00010000<br /><br /> 0x00000000|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_controlfp_s`|\<float.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_contrlfp_s.c  
// processor: x86  
// This program uses _controlfp_s to output the FP control   
// word, set the precision to 24 bits, and reset the status to   
// the default.  
//  
  
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
  
## Sortie  
  
```  
Original: 0x9001f  
0.1 * 0.1 = 1.000000000000000e-002  
24-bit:   0xa001f  
0.1 * 0.1 = 9.999999776482582e-003  
Default:  0x9001f  
0.1 * 0.1 = 1.000000000000000e-002  
```  
  
## Équivalent .NET Framework  
 Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [\_clear87, \_clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [\_status87, \_statusfp, \_statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)   
 [\_control87, \_controlfp, \_\_control87\_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)