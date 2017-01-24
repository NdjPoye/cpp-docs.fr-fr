---
title: "_fcvt | Microsoft Docs"
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
  - "_fcvt"
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
  - "_fcvt"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fcvt (fonction)"
  - "convertir une virgule flottante, en chaînes"
  - "fcvt (fonction)"
  - "fonctions en virgule flottante"
  - "fonctions en virgule flottante, convertir un nombre en chaîne"
ms.assetid: 74584c88-f0dd-4907-8fca-52da5df583f5
caps.latest.revision: 24
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _fcvt
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit un nombre à virgule flottante en une chaîne  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [\_fcvt\_s](../../c-runtime-library/reference/fcvt-s.md).  
  
## Syntaxe  
  
```  
char *_fcvt(   
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
 Nombre de chiffres après la virgule.  
  
 `dec`  
 Pointeur vers l'emplacement de la virgule décimale stockée.  
  
 `sign`  
 Pointeur vers l'indicateur de signe stocké.  
  
## Valeur de retour  
 `_fcvt` retourne un pointeur vers la chaîne de chiffres, la valeur NULL en cas d'erreur.  
  
## Notes  
 La fonction `_fcvt` convertit un nombre à virgule flottante en une chaîne de caractères terminés par null.  Le paramètre `value` est le nombre à virgule flottante à convertir.  `_fcvt` stocke les chiffres de `value` en tant que chaîne et ajoute un caractère NULL \("\\0 "\).  La paramètre `count` spécifie le nombre de chiffres à stocker après la virgule décimale.  Les données en excès sont arrondis aux emplacements `count`.  S'il y a moins de chiffres de précision que `count`, la chaîne est complétées avec des zéros.  
  
 Le nombre total de chiffres retournés par `_fcvt` n'excédera pas `_CVTBUFSIZE`.  
  
 Seules les chiffres sont stockés dans la chaîne.  La position de la virgule décimale et le signe de `value` peuvent être obtenus à partir de `dec` et du signe après l'appel.  Le paramètre `dec` pointe sur une valeur entière donnant la position de la virgule décimale par rapport au début de la chaine.  Un entier nul ou négatif indique que la virgule décimale se trouve à gauche du premier chiffre.  Le paramètre `sign` pointe vers un entier qui indique le signe de `value`.  L'entier est défini à 0 si `value` est positif est défini sur un nombre différent de zéro si `value` est négatif.  
  
 La différence entre `_ecvt` et `_fcvt` réside dans la traduction du paramètre d' `count`.  `_ecvt` interprète `count` comme le nombre total de chiffres dans la chaîne de sortie, alors que `_fcvt` interprète `count` comme le nombre de chiffres après la virgule.  
  
 `_ecvt` et `_fcvt` utilisent une seule mémoire tampon statiquement allouée pour la conversion.  Chaque appel à une de ces routines détruit les résultats de l'appel précédent.  
  
 Cette fonction valide ses paramètres.  Si `dec` ou `sign` a la valeur NULL, ou si `count` vaut 0, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, `errno` est défini à la valeur `EINVAL` et NULL est retourné.  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`_fcvt`|\<stdlib.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_fcvt.c  
// compile with: /W3  
// This program converts the constant  
// 3.1415926535 to a string and sets the pointer  
// buffer to point to that string.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int  decimal, sign;  
   char *buffer;  
   double source = 3.1415926535;  
  
   buffer = _fcvt( source, 7, &decimal, &sign ); // C4996  
   // Note: _fcvt is deprecated; consider using _fcvt_s instead  
   printf( "source: %2.10f   buffer: '%s'   decimal: %d   sign: %d\n",  
            source, buffer, decimal, sign );  
}  
```  
  
  **source: 3.1415926535   mémoire tampon: '31415927'   decimal: 1   signe: 0**   
## Équivalent .NET Framework  
 [System::Convert::ToString](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [\_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [\_gcvt](../../c-runtime-library/reference/gcvt.md)