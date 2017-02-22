---
title: "_control87, _controlfp, __control87_2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_control87"
  - "_controlfp"
  - "__control87_2"
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
  - "_control87"
  - "__control87_2"
  - "control87"
  - "_controlfp"
  - "controlfp"
  - "control87_2"
  - "_control87_2"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__control87_2 (fonction)"
  - "_control87 (fonction)"
  - "_controlfp (fonction)"
  - "control87 (fonction)"
  - "control87_2 (fonction)"
  - "controlfp (fonction)"
  - "EM_AMBIGUOUS"
  - "fonctions en virgule flottante"
  - "fonctions en virgule flottante, définir un mot de commande"
  - "chiffres à virgule flottante, mot de commande"
ms.assetid: 0d09729d-d9a0-43d6-864c-43ff25e7e0c5
caps.latest.revision: 34
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 34
---
# _control87, _controlfp, __control87_2
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient et définit le mot de contrôle à virgule flottante.  Un version plus sûr de `_controlfp` est disponible ; consultez [\_controlfp\_s](../../c-runtime-library/reference/controlfp-s.md).  
  
## Syntaxe  
  
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
  
#### Paramètres  
 `new`  
 Nouvelles valeurs des bits du mot de contrôle.  
  
 `mask`  
 Masque pour de nouveaux bits du mot de contrôle à définir.  
  
 `x86_cw`  
 Rempli par le mot de contrôle pour l'unité à virgule flottante x87.  Passez 0 \(`NULL`\) pour définir uniquement le mot de contrôle SSE2.  
  
 `sse2_cw`  
 Mot de contrôle pour l'unité à virgule flottante de SSE.  Passez 0 \(`NULL`\) pour définir uniquement le mot de contrôle x87.  
  
## Valeur de retour  
 Pour `_control87` et `_controlfp`, les bits de la valeur retournée indiquent l'état du contrôle de virgule flottante.  Pour une définition complète des bits retournés par `_control87`, consultez FLOAT.H.  
  
 Pour `__control87_2`, la valeur de retour est 1, qui indique le succès.  
  
## Notes  
 La fonction `_control87` obtient et définit le mot de contrôle de virgule flottante.  Le mot de contrôle de virgule flottante permet au programme de modifier la précision, l'arrondi, et les modes infinis dans le package mathématiques à virgule flottante, selon la plateforme.  Vous pouvez également utiliser `_control87` pour masquer ou démasquer des exceptions de virgule flottante.  Si la valeur de `mask` est égale à 0, `_control87` obtient le mot de contrôle de virgule flottante.  Si `mask` est différent de zéro, une nouvelle valeur pour le mot de contrôle est définie : Pour tout bit qui est activé \(autrement dit, égal à 1\) dans `mask`, le bit correspondant dans `new` est utilisé pour mettre à jour le mot de contrôle.  En d'autres termes, `fpcntrl` `=` \(\(`fpcntrl` `& ~mask`\) &#124; \(`new & mask`\)\) où `fpcntrl` correspond au mot de contrôle de virgule flottante.  
  
> [!NOTE]
>  Par défaut, les bibliothèques runtime masquent toutes les exceptions de virgule flottante.  
  
 `_controlfp` est une version portable et indépendante de la plateforme de `_control87`.  Elle est presque identique à la fonction `_control87` sur Intel \(x86\), [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], et sur plateformes ARM.  Si vous ciblez les plateformes x86, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], ou ARM, utilisez `_control87` ou `_controlfp`.  
  
 La différence entre `_control87` et `_controlfp` réside dans la façon dont ils traitent des valeurs dénormalisées.  Pour les plateformes Intel \(x86\), [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], et ARM, `_control87` peut définir et effacer le masque d'exception d'opérandes dénormalisées.  `_controlfp` ne modifie pas le masque d'exception d'opérande dénormalisée.  Cet exemple illustre la différence :  
  
```  
_control87( _EM_INVALID, _MCW_EM );   
// DENORMAL is unmasked by this call  
_controlfp( _EM_INVALID, _MCW_EM );   
// DENORMAL exception mask remains unchanged  
```  
  
 Les valeurs possibles pour la constante de masque \(`mask`\) et les nouvelles valeurs de contrôle \(`new`\) s'affichent dans le tableau de valeurs hexadécimales suivant.  Utilisez les constantes portables répertoriées ci\-dessous \(`_MCW_EM`, `_EM_INVALID`, etc.\) comme arguments à ces fonctions, plutôt qu'en fournissant des valeurs hexadécimales explicitement.  
  
 Les plateformes dérivées d'Intel \(x86\) prennent en charge les valeurs d'entrée et de sortie dénormalisées au niveau matériel.  Le comportement de x86 est de conserver les valeurs dénormalisées.  La plateforme ARM et les plateformes [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] qui prennent en charge SSE2 autorisent des opérandes et des résultats dénormalisés à être nettoyés ou à être forcés à zéro.  Les fonctions `_controlfp` et `_control87` fournissent un masque pour modifier ce comportement.  L'exemple suivant illustre l'utilisation de ce mask :  
  
```  
_controlfp(_DN_SAVE, _MCW_DN);     
// Denormal values preserved on ARM platforms and on x64 processors with  
// SSE2 support. NOP on x86 platforms.  
_controlfp(_DN_FLUSH, _MCW_DN);     
// Denormal values flushed to zero by hardware on ARM platforms   
// and x64 processors with SSE2 support. Ignored on other x86 platforms.  
```  
  
 Sur les plateformes ARM, les fonctions `_control87` et `_controlfp` s'appliquent au registre de FPSCR.  Sur les architectures [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], seul le mot de contrôle de SSE2 qui est stocké dans le registre de MXCSR est affecté.  Sur les plateformes Intel \(x86\), `_control87` et `_controlfp` affectent les mots de contrôle pour le x87 et le SSE2, le cas échéant.  La fonction `__control87_2` active les unités à virgule flottante de x87 et SSE2 à contrôler ensemble ou séparément.  Si vous souhaitez assigner les deux unités, passez les adresses de deux entiers à `x86_cw` et `sse2_cw`.  Si vous ne souhaitez affecter qu'une unité, passez une adresse pour ce paramètre mais passez 0 \(null\) pour l'autre.  Si 0 est passée pour un de ces paramètres, la fonction n'a aucun effet sur cette unité à virgule flottante.  Cette fonctionnalité peut être utile dans les situations où une partie du code utilise l'unité à virgule flottante de x87 et une autre partie du code utilise l'unité à virgule flottante de SSE2.  Si vous utilisez `__control87_2` dans une partie d'un programme et définissez des valeurs différentes pour les mots de contrôle de virgule flottante, et utilisez ensuite `_control87` ou `_controlfp` pour manipuler davantage le mot de contrôle, alors il est possible que `_control87` et `_controlfp` ne puissent pas retourner un mot de contrôle unique pour représenter l'état des deux unités à virgule flottante.  Dans ce cas, ces fonctions définissent l'indicateur `EM_AMBIGUOUS` dans la valeur entière retournée pour indiquer qu'il existe une incohérence entre les deux mots de contrôle.  Ceci avertit que le mot de contrôle retourné peut ne pas représenter exactement l'état des deux mots de commande à virgule flottante.  
  
 Sur les architectures ARM et [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], modifier le mode infini ou la précision de la virgule flottante n'est pas pris en charge.  Si le masque de contrôle de précision est utilisé sur la plateforme [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], la fonction lève une assertion et le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  
  
> [!NOTE]
>  `__control87_2` n'est pas pris en charge sur les architectures ARM ou [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)].  Si vous utilisez `__control87_2` et compilez votre programme pour les architectures ARM ou [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], le compilateur génère une erreur.  
  
 Ces fonctions sont ignorées lorsque vous utilisez [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md) ou `/clr:pure` pour compiler car le Common Langage Runtime \(CLR\) ne prend en charge que la précision de virgule flottante par défaut.  
  
 **Valeurs hexadécimales**  
  
 Pour le masque `_MCW_EM`, le nettoyage du masque définit l'exception, ce qui permet l'exception matérielle ; la définition du masque masque l'exception.  Si un `_EM_UNDERFLOW` ou un `_EM_OVERFLOW` se produit, aucune exception matérielle n'est levée jusqu'à ce que l'instruction à virgule flottante suivante soit exécutée.  Pour générer une exception matérielle immédiatement après `_EM_UNDERFLOW` ou `_EM_OVERFLOW`, appelez l'instruction MASM `FWAIT`.  
  
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
|`_control87`, `_controlfp`, `_control87_2`|\<float.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_cntrl87.c  
// processor: x86  
// This program uses __control87_2 to output the x87 control   
// word, set the precision to 24 bits, and reset the status to   
// the default.  
//  
  
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
  
## Sortie  
  
```  
Original: 0x0001  
0.1 * 0.1 = 1.000000000000000e-002  
24-bit:   0x0001  
0.1 * 0.1 = 9.999999776482582e-003  
Default:  0x0001  
0.1 * 0.1 = 1.000000000000000e-002  
```  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [\_clear87, \_clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [\_status87, \_statusfp, \_statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)   
 [\_controlfp\_s](../../c-runtime-library/reference/controlfp-s.md)