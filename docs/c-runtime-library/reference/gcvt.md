---
title: "_gcvt | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_gcvt"
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
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_gcvt"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CVTBUFSIZE"
  - "_gcvt (fonction)"
  - "conversions, de virgule flottante en chaînes"
  - "CVTBUFSIZE"
  - "fonctions en virgule flottante, convertir un nombre en chaîne"
  - "gcvt (fonction)"
  - "nombres, convertir en chaînes"
  - "chaînes (C++), convertir à partir de valeurs à virgule flottante"
ms.assetid: 5761411e-c06b-409a-912f-810fe7f4bcb5
caps.latest.revision: 25
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _gcvt
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit une valeur en virgule flottante en une chaîne, qu'elle stocke dans une mémoire tampon.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [\_gcvt\_s](../../c-runtime-library/reference/gcvt-s.md).  
  
## Syntaxe  
  
```  
char *_gcvt(   
   double value,  
   int digits,  
   char *buffer   
);  
```  
  
#### Paramètres  
 `value`  
 Valeur à convertir.  
  
 `digits`  
 Nombre de chiffres significatifs stockés.  
  
 `buffer`  
 Emplacement de stockage du résultat.  
  
## Valeur de retour  
 `_gcvt` retourne un pointeur vers la chaîne de chiffres.  
  
## Notes  
 La fonction `_gcvt` convertit un `value` à virgule flottante en une chaîne de caractères \(incluant une virgule et éventuellement un octet de signe\) et enregistre la chaîne dans `buffer`.  `buffer` doit être suffisamment grande pour contenir la valeur convertie et un caractère NULL de fin, qui est ajouté automatiquement.  Si une taille de mémoire tampon valant `digits` \+ 1 est utilisée, la fonction remplace la fin de la mémoire tampon.  Cela est dû au fait que la chaîne convertie inclut une virgule et peut contenir des informations de signe et d'exposant.  Il n'y a aucune provision pour un dépassement de capacité.  `_gcvt` tente de générer des chiffres `digits` au format décimal.  S'il est impossible, il génère des chiffres `digits` au format exponentiel.  Les zéros à droite peuvent être supprimés de la conversion.  
  
 Une `buffer` de longueur `_CVTBUFSIZE` est suffisante pour n'importe quelle valeur à virgule flottante.  
  
 Cette fonction valide ses paramètres.  Si `buffer` est `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction paramètre `errno` à `EINVAL` et renvoie `NULL`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_gcvt`|\<stdlib.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_gcvt.c  
// compile with: /W3  
#include <stdlib.h>  
#include <stdio.h>  
#include <string.h>  
  
int main( void )  
{  
   char buffer[_CVTBUFSIZE];  
   double value = -1234567890.123;  
   printf( "The following numbers were converted by _gcvt(value,12,buffer):\n" );  
   _gcvt( value, 12, buffer ); // C4996  
   // Note: _gcvt is deprecated; consider using _gcvt_s instead  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value *= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value *= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value *= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
  
   printf( "\n" );  
   value = -12.34567890123;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value /= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value /= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value /= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
}  
```  
  
  **Les valeurs suivantes ont été convertis par le \_gcvt \(valeur, 12, tampon\) :**  
**mémoire tampon : « 1234567890,12 " \(14 caractères\)**  
**mémoire tampon : '\-12345678901.2' \(14 caractères\)**  
**mémoire tampon : '\-123456789012' \(13 caractères\)**  
**mémoire tampon : '\-1.23456789012e\+012' \(19 caractères\)**  
**mémoire tampon : '\-12.3456789012' \(14 caractères\)**  
**mémoire tampon : '\-1.23456789012' \(14 caractères\)**  
**mémoire tampon : '\-0.123456789012' \(15 caractères\)**  
**mémoire tampon : '\-1.23456789012e\-002' \(19 caractères\)**   
## Équivalent .NET Framework  
 [System::Convert::ToString](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [\_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [\_fcvt](../../c-runtime-library/reference/fcvt.md)