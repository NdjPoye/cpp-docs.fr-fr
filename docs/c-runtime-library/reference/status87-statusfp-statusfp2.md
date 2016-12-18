---
title: "_status87, _statusfp, _statusfp2 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_statusfp2"
  - "_statusfp"
  - "_status87"
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
  - "_statusfp2"
  - "_statusfp"
  - "statusfp2"
  - "_status87"
  - "status87"
  - "statusfp"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "fonctions à virgule flottante, obtenir le mot de l’état"
  - "nombres à virgule flottante, mot de l’état"
  - "status87 (fonction)"
  - "mot de l’état, obtenir la virgule flottante"
  - "statusfp (fonction)"
  - "_statusfp (fonction)"
  - "_statusfp2 (fonction)"
  - "statusfp2 (fonction)"
  - "_status87 (fonction)"
  - "fonctions en virgule flottante"
  - "mot de l'état"
ms.assetid: 7ef963fa-b1fb-429d-94d6-fbf282ab7432
caps.latest.revision: 20
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _status87, _statusfp, _statusfp2
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient le mot d'état à virgule flottante.  
  
## Syntaxe  
  
```  
unsigned int _status87( void );  
unsigned int _statusfp( void );  
void _statusfp2(unsigned int *px86, unsigned int *pSSE2)  
```  
  
#### Paramètres  
 `px86`  
 Cette adresse est remplie avec le mot d'état pour l'unité à virgule flottante x87.  
  
 `pSSE2`  
 Cette adresse est remplie avec le mot d'état pour l'unité à virgule flottante SSE2.  
  
## Valeur de retour  
 Pour `_status87` et `_statusfp`, les bits de la valeur retournée montrent l'état de la virgule flottante.  Consultez le fichier include de FLOAT.H pour une définition des bits retournés par `_statusfp`.  De nombreuses fonctions de la bibliothèque mathématique modifient le mot d'état à virgule flottante, avec des résultats imprévisibles.  L'optimisation peut réorganiser, combiner, et éliminer les opérations en virgule flottante autour des appels à `_status87`, `_statusfp`, et aux fonctions liées.  Utilisez l'option du compilateur [\/Od \(Désactiver \(Débogage\)\)](../../build/reference/od-disable-debug.md) ou la directive pragma [fenv\_access](../../preprocessor/fenv-access.md) pour empêcher les optimisations qui modifient l'ordre des opérations en virgule flottante.  Les valeurs de retour de `_clearfp` et `_statusfp`, ainsi que les paramètres de retour de `_statusfp2`, sont plus fiables quand moins d'opérations en virgule flottante sont exécutées entre les états connus du mot d'état à virgule flottante.  
  
## Notes  
 La fonction `_statusfp` obtient le mot d'état à virgule flottante.  Le mot d'état est une combinaison de l'état du processeur à virgule flottante et d'autres conditions détectées par le gestionnaire d'exception à virgule flottante \- par exemple, le dépassement de capacité de la pile à virgule flottante \(positif ou négatif\).  Les exceptions démasquées sont vérifiées avant que le contenu du mot d'état soit retourné.  Cela signifie que l'appelant est informé des exceptions en attente.  Sur les plateformes x86, `_statusfp` retourne une combinaison de l'état de la virgule flottante x87 et SSE2.  Sur les plateformes x64, l'état retourné est selon l'état du MXCSR du SSE.  Sur les plateformes ARM, `_statusfp` retourne l'état du registre de FPSCR.  
  
 `_statusfp` est une version portable et indépendante de la plateforme de `_status87`.  Elle est identique à `_status87` sur les plateformes Intel \(x86\) et est également prise en charge par x64 et les plateformes ARM.  Pour vous assurer que votre code à virgule flottante est portable à toutes les architectures, utilisez `_statusfp`.  Si vous ciblez uniquement les plateformes x86, vous pouvez utiliser `_status87` ou `_statusfp`.  
  
 Nous vous recommandons `_statusfp2` pour les processeurs \(tels que Pentium IV\) qui possèdent un x87 et un processeur SSE2 à virgule flottante.  Pour `_statusfp2`, les adresses sont remplies à l'aide du mot d'état à virgule flottante pour le x87 ou processeur SSE2 à virgule flottante.  Pour un processeur qui prend en charge les processeurs x87 et SSE2 à virgule flottante, EM\_AMBIGUOUS a la valeur 1 si `_statusfp` ou `_controlfp` est utilisé et que l'action était ambiguë car il pourrait faire référence au mot d'état à virgule flottante x87 ou SSE2.  La fonction `_statusfp2` est prise en charge uniquement sur les plateformes x86.  
  
 Ces fonctions ne sont pas utiles pour [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md) ou pour la compilation `/clr:pure` car le Common Langage Runtime \(CLR\) prend uniquement en charge la précision de virgule flottante par défaut.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_status87`, `_statusfp`, `_statusfp2`|\<float.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
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
  
  **État \= 0x00000000 \- espace libre**  
**État \= 0x00000003 \- incorrect, dépassement de capacité négatif**  
**État \= 0x00080003 \- incorrect, dépassement de capacité, denormal**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [\_clear87, \_clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [\_control87, \_controlfp, \_\_control87\_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)