---
title: "_ecvt | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ecvt"
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
  - "_ecvt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ecvt (fonction)"
  - "convertir des nombres doubles"
  - "ecvt (fonction)"
  - "nombres, convertir"
ms.assetid: a916eb05-92d1-4b5c-8563-093acdb49dc8
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _ecvt
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit un nombre `double` en une chaine.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [\_ecvt\_s](../../c-runtime-library/reference/ecvt-s.md).  
  
## Syntaxe  
  
```  
char *_ecvt(   
   double value,  
   int count,  
   int *dec,  
   int *sign   
);  
```  
  
#### Paramètres  
 `value`  
 Nombre devant être converti.  
  
 `count`  
 Nombre de chiffres stockés.  
  
 `dec`  
 Position de la virgule décimale stockée.  
  
 `sign`  
 Signe du nombre converti.  
  
## Valeur de retour  
 `_ecvt` retourne un pointeur vers la chaîne de chiffres ; NULL si une erreur se produit.  
  
## Notes  
 La fonction `_ecvt` convertit un nombre à virgule flottante en une chaîne de caractères.  Le paramètre `value` est le nombre à virgule flottante à convertir.  Cette fonction garde jusqu'à `count` chiffres de `value` en tant que chaîne et ajoute un caractère NULL \("\\0 "\).  Si le nombre de chiffres dans `value` dépasse `count`, le chiffre d'ordre le plus bas est arrondi.  S'il y a moins de chiffres que `count`, la chaîne est complétées avec des zéros.  
  
 Le nombre total de chiffres retournés par `_ecvt` n'excédera pas `_CVTBUFSIZE`.  
  
 Seules les chiffres sont stockés dans la chaîne.  La position de la virgule décimale et le signe de `value` peuvent être obtenus à partir de `dec` et de `sign` après l'appel.  Le paramètre `dec` pointe sur une valeur entière donnant la position de la virgule décimale par rapport au début de la chaine.  Un entier nul ou négatif indique que la virgule décimale se trouve à gauche du premier chiffre.  Le paramètre `sign` pointe sur un entier qui indique le signe du nombre converti.  Si la valeur entière est 0, le nombre est positif.  Sinon, le nombre est négatif.  
  
 La différence entre `_ecvt` et `_fcvt` réside dans la traduction du paramètre d' `count`.  `_ecvt` interprète `count` comme le nombre total de chiffres dans la chaîne de sortie, alors que `_fcvt` interprète `count` comme le nombre de chiffres après la virgule.  
  
 `_ecvt` et `_fcvt` utilisent une seule mémoire tampon statiquement allouée pour la conversion.  Chaque appel à une de ces routines détruit le résultat de l'appel précédent.  
  
 Cette fonction valide ses paramètres.  Si `dec` ou `sign` a la valeur NULL, ou si `count` ivaut 0, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, `errno` est défini à la valeur `EINVAL` et NULL est retourné.  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`_ecvt`|\<stdlib.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_ecvt.c  
// compile with: /W3  
// This program uses _ecvt to convert a  
// floating-point number to a character string.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int     decimal,   sign;  
   char    *buffer;  
   int     precision = 10;  
   double  source = 3.1415926535;  
  
   buffer = _ecvt( source, precision, &decimal, &sign ); // C4996  
   // Note: _ecvt is deprecated; consider using _ecvt_s instead  
   printf( "source: %2.10f   buffer: '%s'  decimal: %d  sign: %d\n",  
           source, buffer, decimal, sign );  
}  
```  
  
  **source: 3.1415926535   mémoire tampon: '3141592654' decimal: 1 signe: 0**   
## Équivalent .NET Framework  
 [System::Convert::ToString](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [\_fcvt](../../c-runtime-library/reference/fcvt.md)   
 [\_gcvt](../../c-runtime-library/reference/gcvt.md)