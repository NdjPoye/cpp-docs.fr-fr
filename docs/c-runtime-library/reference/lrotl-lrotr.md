---
title: "_lrotl, _lrotr | Microsoft Docs"
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
  - "_lrotl"
  - "_lrotr"
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
  - "api-ms-win-crt-utility-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "lrotr"
  - "lrotl"
  - "_lrotr"
  - "_lrotl"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_lrotl (fonction)"
  - "_lrotr (fonction)"
  - "bits"
  - "bits, faire pivoter"
  - "lrotl (fonction)"
  - "lrotr (fonction)"
  - "faire pivoter les bits"
ms.assetid: d42f295b-35f9-49d2-9ee4-c66896ffe68e
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _lrotl, _lrotr
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fait pivoter les bits vers la gauche \(`_lrotl`\) ou la droite \(`_lrotr`\).  
  
## Syntaxe  
  
```  
  
      unsigned long _lrotl(  
   unsigned long value,  
   int shift   
);  
unsigned long _lrotr(  
   unsigned long value,  
   int shift   
);  
```  
  
#### Paramètres  
 *correspondante*  
 Valeur à faire pivoter.  
  
 `shift`  
 Nombre de bits pour déplacer *la valeur*.  
  
## Valeur de retour  
 Les deux fonctions retournent la valeur pivotée.  Aucun retour d'erreur.  
  
## Notes  
 Les fonctions `_lrotl` et les fonctions `_lrotr` font pivoter *la valeur* par `shift`\(glissement\) des bits.  `_lrotl` pivote la valeur de gauche.  `_lrotr` pivote la valeur de droite.  Les deux fonctions enveloppent les bits pivotés à partir *de la valeur* jusqu'à l'autre extrémité.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_lrotl`|\<stdlib.h\>|  
|`_lrotr`|\<stdlib.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
  
```  
// crt_lrot.c  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   unsigned long val = 0x0fac35791;  
  
   printf( "0x%8.8lx rotated left eight times is 0x%8.8lx\n",   
            val, _lrotl( val, 8 ) );  
   printf( "0x%8.8lx rotated right four times is 0x%8.8lx\n",   
            val, _lrotr( val, 4 ) );  
}  
```  
  
## Sortie  
  
```  
0xfac35791 rotated left eight times is 0xc35791fa  
0xfac35791 rotated right four times is 0x1fac3579  
```  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [\_rotl, \_rotl64, \_rotr, \_rotr64](../../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)