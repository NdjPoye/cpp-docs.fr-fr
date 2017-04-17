---
title: "mktime, _mktime32, _mktime64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mktime32"
  - "mktime"
  - "_mktime64"
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
  - "api-ms-win-crt-time-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "mktime"
  - "_mktime64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mktime32 (fonction)"
  - "_mktime64 (fonction)"
  - "convertir des heures"
  - "mktime (fonction)"
  - "mktime32 (fonction)"
  - "mktime64 (fonction)"
  - "fonctions d'heure"
  - "heure, convertir"
ms.assetid: 284ed5d4-7064-48a2-bd50-15effdae32cf
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# mktime, _mktime32, _mktime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit l'heure locale en valeur de calendrier.  
  
## Syntaxe  
  
```  
time_t mktime(  
   struct tm *timeptr   
);  
__time32_t _mktime32(  
   struct tm *timeptr   
);  
__time64_t _mktime64(  
   struct tm *timeptr   
);  
```  
  
#### Paramètres  
 *timeptr*  
 Pointeur vers la structure d'heure ; voir [asctime](../../c-runtime-library/reference/asctime-wasctime.md).  
  
## Valeur de retour  
 `_mktime32` retourne l'heure de calendrier spécifiée encodée sous forme de valeur de type [time\_t](../../c-runtime-library/standard-types.md). Si *timeptr* référence une date antérieure au 1er janvier 1970 à minuit ou si l'heure de calendrier ne peut pas être représentée, `_mktime32` retourne –1 \(cast vers le type `time_t`\). Lorsque vous utilisez `_mktime32` et *timeptr* référence une date postérieure 23:59:59 18 janvier 2038, temps universel coordonné \(UTC\), elle retourne – 1 castée en type `time_t`.  
  
 `_mktime64` retourne –1 \(cast vers le type `__time64_t`\) si *timeptr* référence une date postérieure au 31 décembre 3000 à 23:59:59, heure UTC.  
  
## Notes  
 Les fonctions `mktime`, `_mktime32` et `_mktime64` convertissent la structure d'heure fournie \(peut\-être incomplète\) pointée par *timeptr* en une structure entièrement définie avec des valeurs normalisées, puis la convertit en valeur d'heure de calendrier `time_t`. L'heure convertie a le même encodage que les valeurs retournées par la fonction [time](../../c-runtime-library/reference/time-time32-time64.md). Les valeurs d'origine des composants `tm_wday` et `tm_yday` de la structure *timeptr* sont ignorées, et les valeurs d'origine des autres composants ne sont pas limitées à leurs plages normales.  
  
 `mktime` est une fonction inline équivalente à `_mktime64`, sauf si `_USE_32BIT_TIME_T` est défini. Dans ce cas, elle équivaut à `_mktime32`.  
  
 Après un ajustement au format UTC, `_mktime32` gère les dates à partir du 1er janvier 1970 à minuit à 23:59:59 18 janvier 2038, UTC.`_mktime64` gère les dates comprises entre le 1er janvier 1970 à minuit et le 31 décembre 3000 à 23:59:59. Cet ajustement peut amener ces fonctions à retourner \-1 \(cast en `time_t`, `__time32_t` ou `__time64_t`\) même si la date que vous spécifiez se situe dans la plage. Par exemple, si vous êtes au Caire en Égypte, où le décalage horaire est de \+2 heures par rapport à l'heure UTC, deux heures seront d'abord soustraites de la date que vous spécifiez dans *timeptr*, ce qui risque de faire sortir votre date de la plage.  
  
 Ces fonctions peuvent être utilisées pour valider et compléter une structure tm. Si elles aboutissent, ces fonctions définissent si nécessaire les valeurs de `tm_wday` et `tm_yday`, ainsi que les autres composants afin de représenter l'heure de calendrier spécifiée, mais avec des valeurs maintenues dans les plages normales. La valeur finale de `tm_mday` n'est pas définie tant que `tm_mon` et `tm_year` ne sont pas déterminés. Au moment de spécifier une heure de structure `tm`, affectez au champ `tm_isdst` l'une des valeurs suivantes :  
  
-   zéro \(0\) pour indiquer que l'heure d'hiver est active ;  
  
-   une valeur supérieure à 0 pour indiquer que l'heure d'été est active ;  
  
-   une valeur inférieure à zéro pour que le code de la bibliothèque Runtime C calcule si l'heure active est l'heure d'hiver ou l'heure d'été.  
  
 La bibliothèque Runtime C détermine le comportement d'heure d'été à partir de la variable d'environnement [TZ](../../c-runtime-library/reference/tzset.md). Si `TZ` n’est pas défini, l’appel d’API Win32 [GetTimeZoneInformation](http://msdn.microsoft.com/library/windows/desktop/ms724421.aspx) est utilisée pour obtenir des informations au moment de l’heure du système d’exploitation. En cas d'échec, la bibliothèque part du principe que les règles de calcul de l'heure d'été sont celles des États\-Unis.`tm_isdst` est un champ obligatoire. S'il n'est pas défini, sa valeur est indéfinie et la valeur de retour de ces fonctions est imprévisible. Si *timeptr* pointe vers une structure `tm` retournée par un appel antérieur à `asctime`, `gmtime` ou `localtime` \(ou des variantes de ces fonctions\), le champ `tm_isdst` contient la valeur appropriée.  
  
 Notez que `gmtime` et `localtime` \(ainsi que `_gmtime32`, `_gmtime64`, `_localtime32` et `_localtime64`\) utilise une seule mémoire tampon par thread pour la conversion. Si vous fournissez cette mémoire tampon à `mktime`, `_mktime32` ou `_mktime64`, le contenu précédent est détruit.  
  
 Ces fonctions valident leur paramètre. Si *timeptr* est un pointeur null, le Gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, ces fonctions retournent \-1 et définissent `errno` avec la valeur `EINVAL`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`mktime`|\<time.h\>|  
|`_mktime32`|\<time.h\>|  
|`_mktime64`|\<time.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
  
```  
// crt_mktime.c  
/* The example takes a number of days  
 * as input and returns the time, the current  
 * date, and the specified number of days.  
 */  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
   struct tm  when;  
   __time64_t now, result;  
   int        days;  
   char       buff[80];  
  
   time( &now );  
   _localtime64_s( &when, &now );  
   asctime_s( buff, sizeof(buff), &when );  
   printf( "Current time is %s\n", buff );  
   days = 20;  
   when.tm_mday = when.tm_mday + days;  
   if( (result = mktime( &when )) != (time_t)-1 ) {  
      asctime_s( buff, sizeof(buff), &when );  
      printf( "In %d days the time will be %s\n", days, buff );  
   } else  
      perror( "mktime failed" );  
}  
```  
  
## Résultat de l'exemple  
  
```  
Current time is Fri Apr 25 13:34:07 2003  
  
In 20 days the time will be Thu May 15 13:34:07 2003  
```  
  
## Équivalent .NET Framework  
 <xref:System.DateTimeOffset.%23ctor%2A>  
  
## Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [\_mkgmtime, \_mkgmtime32, \_mkgmtime64](../../c-runtime-library/reference/mkgmtime-mkgmtime32-mkgmtime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)