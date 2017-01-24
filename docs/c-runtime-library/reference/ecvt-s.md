---
title: "_ecvt_s | Microsoft Docs"
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
  - "_ecvt_s"
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
  - "ecvt_s"
  - "_ecvt_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ecvt_s (fonction)"
  - "convertir des nombres doubles"
  - "ecvt_s (fonction)"
  - "nombres, convertir"
ms.assetid: d52fb0a6-cb91-423f-80b3-952a8955d914
caps.latest.revision: 25
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ecvt_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit un nombre `double`en une chaine.  Il s'agit de versions de [\_ecvt](../../c-runtime-library/reference/ecvt.md) avec des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
errno_t _ecvt_s(   
   char * _Buffer,  
   size_t _SizeInBytes,  
   double _Value,  
   int _Count,  
   int *_Dec,  
   int *_Sign  
);  
template <size_t size>  
errno_t _ecvt_s(   
   char (&_Buffer)[size],  
   double _Value,  
   int _Count,  
   int *_Dec,  
   int *_Sign  
); // C++ only  
```  
  
#### Paramètres  
 \[out\] `_Buffer`  
 Rempli avec le pointeur vers la chaîne de chiffres, le résultat de la conversion.  
  
 \[in\] `_SizeInBytes`  
 Taille, en octets, de la mémoire tampon.  
  
 \[in\] `_Value`  
 Nombre devant être converti.  
  
 \[in\] `_Count`  
 Nombre de chiffres stockés.  
  
 \[out\] `_Dec`  
 Position de la virgule décimale stockée.  
  
 \[out\] `_Sign`  
 Signe du nombre converti.  
  
## Valeur de retour  
 Zéro en cas de réussite.  La valeur de retour est un code d'erreur en cas de échec.  Les codes d'erreur sont définis dans ERRNO.H.  Pour plus d'informations, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Dans le cas d'un paramètre non valide, comme indiqué dans le tableau suivant, cette fonction appelle le gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction paramètre `errno` à `EINVAL` et renvoie `EINVAL`.  
  
### Conditions d'erreur  
  
|`_Buffer`|`_SizeInBytes`|\_Valeur|\_count|\_Dec|\_Sign|Valeur de retour|Valeur dans `buffer`|  
|---------------|--------------------|--------------|-------------|-----------|------------|----------------------|--------------------------|  
|`NULL`|any|any|any|any|any|`EINVAL`|Non modifié|  
|Non  `NULL` \(pointe vers la mémoire valide\)|\<\=0|any|any|any|any|`EINVAL`|Non modifié|  
|any|any|any|any|`NULL`|any|`EINVAL`|Non modifié|  
|any|any|any|any|any|`NULL`|`EINVAL`|Non modifié|  
  
 **Problèmes de sécurité**  
  
 `_ecvt_s` peut générer une violation d'accès si `buffer` ne pointe pas vers de la mémoire valide est n'est pas `NULL`.  
  
## Notes  
 La fonction `_ecvt_s` convertit un nombre à virgule flottante en une chaîne de caractères.  Le paramètre `_Value` est le nombre à virgule flottante à convertir.  Cette fonction garde jusqu'à un nombre `count` les chiffres de`_Value` en tant que chaîne et ajoute un caractère NULL \("\\0 "\).  Si le nombre de chiffres dans `_Value` dépasse `_Count`, le chiffre d'ordre le plus bas est arrondi.  S'il y a moins de chiffres que`count`, la chaîne est complétées avec des zéros.  
  
 Seules les chiffres sont stockés dans la chaîne.  La position de la virgule décimale et le signe de`_Value` peuvent être obtenus à partir de `_Dec` et de`_Sign` après l'appel.  Le paramètre `_Dec`pointe sur une valeur entière donnant la position de la virgule décimale par rapport au début de la chaine.  Un entier nul ou négatif indique que la virgule décimale se trouve à gauche du premier chiffre.  Le paramètre `_Sign` pointe sur un entier qui indique le signe du nombre converti.  Si la valeur entière est 0, le nombre est positif.  Sinon, le nombre est négatif.  
  
 Une mémoire tampon de longueur `_CVTBUFSIZE` est suffisante pour toute valeur à virgule flottante.  
  
 La différence entre `_ecvt_s` et `_fcvt_s` réside dans la traduction du paramètre d'`_Count`.  `_ecvt_s` interprète `_Count` comme le nombre total de chiffres dans la chaîne de sortie, alors que`_fcvt_s` interprète `_Count` comme le nombre de chiffres après la virgule.  
  
 En C\+\+, l'utilisation de ces fonctions est simplifiée par des surcharges de modèle ; les surcharges peuvent également déduire la longueur de la mémoire tampon automatiquement, en éliminant le besoin de spécifier un argument de taille.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
 Les versions de déboggage de ces fonctions remplissent d'abord la mémoire tampon avec 0xFD.  Pour désactiver ce comportement, utilisez [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
## Configuration requise  
  
|Fonction|En\-tête requis|En\-tête facultatif|  
|--------------|---------------------|-------------------------|  
|`_ecvt_s`|\<stdlib.h\>|\<errno.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// ecvt_s.c  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main( )  
{  
  char * buf = 0;  
  int decimal;  
  int sign;  
  int err;  
  
  buf = (char*) malloc(_CVTBUFSIZE);  
  err = _ecvt_s(buf, _CVTBUFSIZE, 1.2, 5, &decimal, &sign);  
  
  if (err != 0)  
  {  
     printf("_ecvt_s failed with error code %d\n", err);  
     exit(1);  
  }  
  
  printf("Converted value: %s\n", buf);    
  
}  
```  
  
  **Valeur convertie. 12000**   
## Équivalent .NET Framework  
 <xref:System.Convert.ToString%2A>  
  
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [\_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [\_fcvt\_s](../../c-runtime-library/reference/fcvt-s.md)   
 [\_gcvt\_s](../../c-runtime-library/reference/gcvt-s.md)