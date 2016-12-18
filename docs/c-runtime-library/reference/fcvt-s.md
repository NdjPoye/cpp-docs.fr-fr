---
title: "_fcvt_s | Microsoft Docs"
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
  - "_fcvt_s"
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
  - "fcvt_s"
  - "_fcvt_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fcvt_s (fonction)"
  - "convertir une virgule flottante, en chaînes"
  - "fcvt_s (fonction)"
  - "fonctions en virgule flottante, convertir un nombre en chaîne"
ms.assetid: 48671197-1d29-4c2b-a5d8-d2368f5f68a1
caps.latest.revision: 27
caps.handback.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _fcvt_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit un nombre à virgule flottante en une chaîne  Il s'agit de versions de [\_fcvt](../../c-runtime-library/reference/fcvt.md) avec des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
errno_t _fcvt_s(   
   char* buffer,  
   size_t sizeInBytes,  
   double value,  
   int count,  
   int *dec,  
   int *sign   
);  
template <size_t size>  
errno_t _fcvt_s(   
   char (&buffer)[size],  
   double value,  
   int count,  
   int *dec,  
   int *sign   
); // C++ only  
```  
  
#### Paramètres  
 \[out\] `buffer`  
 La mémoire tampon fournie qui contiendra le résultat de la conversion.  
  
 \[in\] `sizeInBytes`  
 Taille, en octets, de la mémoire tampon.  
  
 \[in\] `value`  
 Nombre devant être converti.  
  
 \[in\] `count`  
 Nombre de chiffres après la virgule.  
  
 \[out\] `dec`  
 Pointeur vers l'emplacement de la virgule décimale stockée.  
  
 \[out\] `sign`  
 Pointeur vers l'indicateur de signe stocké.  
  
## Valeur de retour  
 Zéro en cas de réussite.  La valeur de retour est un code d'erreur en cas de échec.  Les codes d'erreur sont définis dans ERRNO.H.  Pour obtenir la liste de ces erreurs, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Dans le cas d'un paramètre non valide, comme indiqué dans le tableau suivant, cette fonction appelle le gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction paramètre `errno` à `EINVAL` et renvoie `EINVAL`.  
  
### Conditions d'erreur  
  
|`buffer`|`sizeInBytes`|par défaut|count|dec|sign|Return|Valeur dans `buffer`|  
|--------------|-------------------|----------------|-----------|---------|----------|------------|--------------------------|  
|`NULL`|any|any|any|any|any|`EINVAL`|Non modifié|  
|Non  `NULL` \(pointe vers la mémoire valide\)|\<\=0|any|any|any|any|`EINVAL`|Non modifié|  
|any|any|any|any|`NULL`|any|`EINVAL`|Non modifié|  
|any|any|any|any|any|`NULL`|`EINVAL`|Non modifié|  
  
 **Problèmes de sécurité**  
  
 `_fcvt_s` peut générer une violation d'accès si `buffer` ne pointe pas vers de la mémoire valide est n'est pas `NULL`.  
  
## Notes  
 La fonction `_fcvt_s` convertit un nombre à virgule flottante en une chaîne de caractères terminés par null.  Le paramètre `value` est le nombre à virgule flottante à convertir.  `_fcvt_s` stocke les chiffres de `value` en tant que chaîne et ajoute un caractère NULL \("\\0 "\).  La paramètre `count` spécifie le nombre de chiffres à stocker après la virgule décimale.  Les données en excès sont arrondis aux emplacements `count`.  S'il y a moins de chiffres de précision que`count`, la chaîne est complétées avec des zéros.  
  
 Seules les chiffres sont stockés dans la chaîne.  La position de la virgule décimale et le signe de`value` peuvent être obtenus à partir de `dec` et de`sign` après l'appel.  Le paramètre `dec`pointe sur une valeur entière donnant la position de la virgule décimale par rapport au début de la chaine.  Un entier nul ou négatif indique que la virgule décimale se trouve à gauche du premier chiffre.  Le paramètre `sign` pointe vers un entier qui indique le signe de `value`.  L'entier est défini à 0 si `value` est positif est défini sur un nombre différent de zéro si `value` est négatif.  
  
 Une mémoire tampon de longueur `_CVTBUFSIZE` est suffisante pour toute valeur à virgule flottante.  
  
 La différence entre `_ecvt_s` et `_fcvt_s` réside dans la traduction du paramètre d'`count`.  `_ecvt_s` interprète `count` comme le nombre total de chiffres dans la chaîne de sortie, et que`_fcvt_s` interprète c`ount` comme le nombre de chiffres après la virgule.  
  
 En C\+\+, l'utilisation de ces fonctions est simplifiée par des surcharges de modèle ; les surcharges peuvent également déduire la longueur de la mémoire tampon automatiquement, en éliminant le besoin de spécifier un argument de taille.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
 Les versions de déboggage de ces fonctions remplissent d'abord la mémoire tampon avec 0xFD.  Pour désactiver ce comportement, utilisez [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
## Configuration requise  
  
|Fonction|En\-tête requis|En\-tête facultatif|  
|--------------|---------------------|-------------------------|  
|`_fcvt_s`|\<stdlib.h\>|\<errno.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
 **Bibliothèques :** toutes les versions [Fonctions de bibliothèque CRT](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
  
```  
// fcvt_s.c  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main()  
{  
  char * buf = 0;  
  int decimal;  
  int sign;  
  int err;  
  
  buf = (char*) malloc(_CVTBUFSIZE);  
  err = _fcvt_s(buf, _CVTBUFSIZE, 1.2, 5, &decimal, &sign);  
  
  if (err != 0)  
  {  
     printf("_fcvt_s failed with error code %d\n", err);  
     exit(1);  
  }  
  
  printf("Converted value: %s\n", buf);    
  
}  
```  
  
  **Valeur convertie. 120000**   
## Équivalent .NET Framework  
 <xref:System.Convert.ToString%2A>  
  
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [\_ecvt\_s](../../c-runtime-library/reference/ecvt-s.md)   
 [\_gcvt\_s](../../c-runtime-library/reference/gcvt-s.md)   
 [\_fcvt](../../c-runtime-library/reference/fcvt.md)