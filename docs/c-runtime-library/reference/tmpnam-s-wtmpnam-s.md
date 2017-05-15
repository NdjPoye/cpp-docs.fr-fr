---
title: tmpnam_s, _wtmpnam_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- tmpnam_s
- _wtmpnam_s
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- tmpnam_s
- _wtmpnam_s
- L_tmpnam_s
dev_langs:
- C++
helpviewer_keywords:
- tmpnam_s function
- file names [C++], creating temporary
- _wtmpnam_s function
- L_tmpnam_s constant
- temporary files, creating
- file names [C++], temporary
- wtmpnam_s function
ms.assetid: e70d76dc-49f5-4aee-bfa2-f1baa2bcd29f
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: c2a7276c8670bf0a3fd56ac8c0df111e82da16de
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="tmpnams-wtmpnams"></a>tmpnam_s, _wtmpnam_s
Génèrent des noms que vous pouvez utiliser pour créer des fichiers temporaires. Ces versions de [tmpnam et _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) intègrent les améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
errno_t tmpnam_s(  
   char * str,  
   size_t sizeInChars   
);  
errno_t _wtmpnam_s(  
   wchar_t *str,  
   size_t sizeInChars   
);  
template <size_t size>  
errno_t tmpnam_s(  
   char (&str)[size]  
); // C++ only  
template <size_t size>  
errno_t _wtmpnam_s(  
   wchar_t (&str)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>Paramètres  
 [out] `str`  
 Pointeur destiné à contenir le nom généré.  
  
 [in] `sizeInChars`  
 Taille de la mémoire tampon en caractères.  
  
## <a name="return-value"></a>Valeur de retour  
 Ces deux fonctions retournent 0 en cas de réussite ou un numéro d’erreur en cas d’échec.  
  
### <a name="error-conditions"></a>Conditions d’erreur  
  
|||||  
|-|-|-|-|  
|`str`|`sizeInChars`|**Valeur de retour**|**Contenu de**  `str`|  
|`NULL`|indifférent|`EINVAL`|non modifié|  
|non `NULL` (pointe vers une mémoire valide)|trop court|`ERANGE`|non modifié|  
  
 Si `str` a la valeur `NULL`, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, ces fonctions attribuent à `errno` la valeur `EINVAL` et retournent `EINVAL`.  
  
## <a name="remarks"></a>Notes  
 Chacune de ces fonctions retourne le nom d’un fichier qui n’existe pas actuellement. `tmpnam_s` retourne un nom unique dans le répertoire de travail actif. Notez que lorsqu’un nom de fichier est précédé d’une barre oblique inverse et d’aucune information de chemin, comme \fname21, cela indique que le nom est valide pour le répertoire de travail actif.  
  
 Pour `tmpnam_s`, vous pouvez stocker ce nom de fichier généré dans `str`. La longueur maximale d’une chaîne retournée par `tmpnam_s` est `L_tmpnam_s`, qui est défini dans STDIO.H. Si `str` a la valeur `NULL`, `tmpnam_s` maintient le résultat dans une mémoire tampon statique interne. Par conséquent, tous les appels suivants détruisent cette valeur. Le nom généré par `tmpnam_s` se compose d’un nom de fichier généré par le programme et, après le premier appel à `tmpnam_s`, d’une extension de fichier constituée de numéros séquentiels en base 32 (.1-.1vvvvvu, quand `TMP_MAX_S` dans STDIO.H a la valeur INT_MAX).  
  
 `tmpnam_s` gère automatiquement les arguments de chaîne de caractères multioctets comme il convient, en identifiant les séquences de caractères multioctets en fonction de la page de codes OEM obtenue du système d’exploitation. `_wtmpnam_s` est une version à caractères larges de `tmpnam_s` ; l'argument et la valeur de retour de `_wtmpnam_s` sont des chaînes à caractères larges. `_wtmpnam_s` et `tmpnam_s` se comportent de la même manière, sauf que `_wtmpnam_s` ne gère pas les chaînes de caractères multioctets.  
  
 En C++, l’utilisation de ces fonctions est simplifiée par les surcharges de modèle ; celles-ci peuvent déduire automatiquement la longueur de la mémoire tampon, ce qui évite d’avoir à spécifier un argument de taille. Pour plus d’informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_ttmpnam_s`|`tmpnam_s`|`tmpnam_s`|`_wtmpnam_s`|  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`tmpnam_s`|\<stdio.h>|  
|`_wtmpnam_s`|\<stdio.h> ou \<wchar.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_tmpnam_s.c  
// This program uses tmpnam_s to create a unique filename in the  
// current working directory.   
//  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{     
   char name1[L_tmpnam_s];  
   errno_t err;  
   int i;  
  
   for (i = 0; i < 15; i++)  
   {  
      err = tmpnam_s( name1, L_tmpnam_s );  
      if (err)  
      {  
         printf("Error occurred creating unique filename.\n");  
         exit(1);  
      }  
      else  
      {  
         printf( "%s is safe to use as a temporary file.\n", name1 );  
      }  
   }    
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de flux](../../c-runtime-library/stream-i-o.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [tmpfile_s](../../c-runtime-library/reference/tmpfile-s.md)
