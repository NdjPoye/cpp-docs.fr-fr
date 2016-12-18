---
title: "_rotl, _rotl64, _rotr, _rotr64 | Microsoft Docs"
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
  - "_rotr64"
  - "_rotl"
  - "_rotr"
  - "_rotl64"
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
  - "_rotr64"
  - "rotl64"
  - "_rotl64"
  - "rotr64"
  - "rotr"
  - "_rotr"
  - "_rotl"
  - "rotl"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_rotl (fonction)"
  - "_rotl64 (fonction)"
  - "_rotr (fonction)"
  - "_rotr64 (fonction)"
  - "bits, faire pivoter"
  - "faire pivoter les bits"
  - "rotl (fonction)"
  - "rotl64 (fonction)"
  - "rotr (fonction)"
  - "rotr64 (fonction)"
ms.assetid: cfce439b-366f-4584-8ab1-d527b13fcfc6
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _rotl, _rotl64, _rotr, _rotr64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fait pivoter les bits vers la gauche \(`_rotl`\) ou la droite \(`_rotr`\).  
  
## Syntaxe  
  
```  
  
      unsigned int _rotl(  
   unsigned int value,  
   int shift   
);  
unsigned __int64 _rotl64(  
   unsigned __int64 value,   
   int shift  
);  
unsigned int _rotr(  
   unsigned int value,  
   int shift   
);  
unsigned __int64 _rotr64(  
   unsigned __int64 value,  
   int shift  
);  
```  
  
#### Paramètres  
 *correspondante*  
 Valeur à faire pivoter.  
  
 `shift`  
 Nombre de bits à déplacer.  
  
## Valeur de retour  
 La valeur déplacée.  Aucun retour d'erreur.  
  
## Notes  
 Les fonctions `_rotl` et `_rotr` font pivoter *la valeur* non signée par `shift`\(déplacement\) de bits.  `_rotl` pivote la valeur de gauche.  `_rotr` pivote la valeur de droite.  Les deux fonctions enveloppent les bits pivotés à partir *de la valeur* jusqu'à l'autre extrémité.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|**\_rotl, \_rotl64**|\<stdlib.h\>|  
|**\_rotr, \_rotr64**|\<stdlib.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
  
```  
// crt_rot.c  
/* This program shifts values to rotate an integer.  
 */  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   unsigned val = 0x0fd93;  
   __int64 val2 = 0x0101010101010101;  
  
   printf( "0x%4.4x rotated left three times is 0x%4.4x\n",   
           val, _rotl( val, 3 ) );  
   printf( "0x%4.4x rotated right four times is 0x%4.4x\n",   
           val, _rotr( val, 4 ) );  
  
   printf( "%I64x rotated left three times is %I64x\n",  
           val2, _rotl64( val2, 3 ) );  
   printf( "%I64x rotated right four times is %I64x\n",   
           val2, _rotr64( val2, 4 ) );  
}  
```  
  
## Sortie  
  
```  
0xfd93 rotated left three times is 0x7ec98  
0xfd93 rotated right four times is 0x30000fd9  
101010101010101 rotated left three times is 808080808080808  
101010101010101 rotated right four times is 1010101010101010  
```  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [\_lrotl, \_lrotr](../../c-runtime-library/reference/lrotl-lrotr.md)