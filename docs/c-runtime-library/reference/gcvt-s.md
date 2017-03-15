---
title: "_gcvt_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_gcvt_s"
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
  - "_gcvt_s"
  - "gcvt_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CVTBUFSIZE"
  - "_gcvt_s (fonction)"
  - "conversions, de virgule flottante en chaînes"
  - "CVTBUFSIZE"
  - "fonctions en virgule flottante, convertir un nombre en chaîne"
  - "gcvt_s (fonction)"
  - "nombres, convertir en chaînes"
  - "chaînes (C++), convertir à partir de valeurs à virgule flottante"
ms.assetid: 0a8d8a26-5940-4ae3-835e-0aa6ec1b0744
caps.latest.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 30
---
# _gcvt_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit une valeur à virgule flottante en une chaîne.  Il s'agit de versions de [\_gcvt](../../c-runtime-library/reference/gcvt.md) avec des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
errno_t _gcvt_s(   
   char *buffer,  
   size_t sizeInBytes,  
   double value,  
   int digits   
);  
template <size_t cchStr>  
errno_t _gcvt_s(   
   char (&buffer)[cchStr],  
   double value,  
   int digits   
); // C++ only  
```  
  
#### Paramètres  
 \[out\] `buffer`  
 Mémoire tampon pour stocker les résultats de la conversion.  
  
 \[in\] `sizeInBytes`  
 Taille de la mémoire tampon.  
  
 \[in\] `value`  
 Valeur à convertir.  
  
 \[in\] `digits`  
 Nombre de chiffres significatifs stockés.  
  
## Valeur de retour  
 Zéro en cas de réussite.  Si une défaillance se produit en raison d'un paramètre non valide \(voir le tableau suivant pour les valeurs valides\), le gestionnaire de paramètre non valide est appelée comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée de continuer, le code d'erreur est retourné.  Les codes d'erreur sont définis dans ERRNO.H.  Pour obtenir la liste de ces erreurs, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
### Conditions d'erreur  
  
|`buffer`|`sizeInBytes`|`value`|`digits`|Return|Valeur dans `buffer`|  
|--------------|-------------------|-------------|--------------|------------|--------------------------|  
|`NULL`|any|any|any|`EINVAL`|Non modifié|  
|Non  `NULL` \(pointe vers la mémoire valide\)|zéro|any|any|`EINVAL`|Non modifié|  
|Non  `NULL` \(pointe vers la mémoire valide\)|any|any|\>\= `sizeInBytes`|`EINVAL`|Non modifié|  
  
 **Problèmes de sécurité**  
  
 `_gcvt_s` peut générer une violation d'accès si `buffer` ne pointe pas vers de la mémoire valide et n'est pas `NULL`.  
  
## Notes  
 La fonction `_gcvt_s` convertit un `value` à virgule flottante en une chaîne de caractères \(incluant une virgule et éventuellement un octet de signe\) et enregistre la chaîne dans `buffer`.  `buffer` doit être suffisamment grande pour contenir la valeur convertie et un caractère NULL de fin, qui est ajouté automatiquement.  Une mémoire tampon de longueur `_CVTBUFSIZE` est suffisante pour toute valeur à virgule flottante.  Si une taille de mémoire tampon d'`digits` \+ 1 est utilisée, la fonction ne remplace pas la fin de la mémoire tampon, veillez à fournir un tampon suffisante pour cette opération.  `_gcvt_s` tente de générer des chiffres `digits` au format décimal.  S'il est impossible, il génère des chiffres `digits` au format exponentiel.  Les zéros à droite peuvent être supprimés de la conversion.  
  
 En C\+\+, l'utilisation de ces fonctions est simplifiée par des surcharges de modèle ; les surcharges peuvent également déduire la longueur de la mémoire tampon automatiquement, en éliminant le besoin de spécifier un argument de taille.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
 Les versions de déboggage de ces fonctions remplissent d'abord la mémoire tampon avec 0xFD.  Pour désactiver ce comportement, utilisez [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|En\-tête facultatif|  
|-------------|---------------------|-------------------------|  
|`_gcvt_s`|\<stdlib.h\>|\<error.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_gcvt_s.c  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main()  
{  
  char buf[_CVTBUFSIZE];  
  int decimal;  
  int sign;  
  int err;  
  
  err = _gcvt_s(buf, _CVTBUFSIZE, 1.2, 5);  
  
  if (err != 0)  
  {  
     printf("_gcvt_s failed with error code %d\n", err);  
     exit(1);  
  }  
  
  printf("Converted value: %s\n", buf);    
  
}  
```  
  
  **Valeur convertie. 1.2**   
## Équivalent .NET Framework  
 <xref:System.Convert.ToString%2A>  
  
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [\_ecvt\_s](../../c-runtime-library/reference/ecvt-s.md)   
 [\_fcvt\_s](../../c-runtime-library/reference/fcvt-s.md)   
 [\_gcvt](../../c-runtime-library/reference/gcvt.md)