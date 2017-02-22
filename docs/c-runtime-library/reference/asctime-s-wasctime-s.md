---
title: "asctime_s, _wasctime_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wasctime_s"
  - "asctime_s"
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
  - "asctime_s"
  - "_wasctime_s"
  - "_tasctime_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tasctime_s (fonction)"
  - "_wasctime_s (fonction)"
  - "asctime_s (fonction)"
  - "tasctime_s (fonction)"
  - "conversion de la structure d'heure"
  - "heure, convertir"
  - "wasctime_s (fonction)"
ms.assetid: 17ad9b2b-a459-465d-976a-42822897688a
caps.latest.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 29
---
# asctime_s, _wasctime_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit un structure temporelle `tm` en une chaîne de caractères.  Ces fonctions sont des versions de [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md) avec des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
errno_t asctime_s(   
   char* buffer,  
   size_t numberOfElements,  
   const struct tm *_tm   
);  
errno_t _wasctime_s(   
   wchar_t* buffer,  
   size_t numberOfElements  
   const struct tm *_tm   
);  
template <size_t size>  
errno_t asctime_s(   
   char (&buffer)[size],  
   const struct tm *_tm   
); // C++ only  
template <size_t size>  
errno_t _wasctime_s(   
   wchar_t (&buffer)[size],  
   const struct tm *_tm   
); // C++ only  
```  
  
#### Paramètres  
 `buffer`  
 \[out\] Un pointeur vers une mémoire tampon pour stocker le résultat de chaîne de caractères.  Cette fonction prend un pointeur vers l'emplacement d'une mémoire valide avec une taille spécifiée par `numberOfElements`.  
  
 `numberOfElements`  
 \[in\] la taille de la mémoire tampon utilisée pour stocker le résultat.  
  
 `_tm`  
 \[in\] Structure Temps\/Date.  Cette fonction prend un pointeur vers un objet valide `struct` `tm`.  
  
## Valeur de retour  
 Zéro en cas de réussite.  S'il y a un échec, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à continuer, la valeur de retour est un code d'erreur.  Les codes d'erreur sont définis dans ERRNO.H.  Pour plus d'informations, consultez [errno, constantes](../../c-runtime-library/errno-constants.md).  Les codes d'erreur réels retournés pour chaque condition d'erreur sont présentés dans le tableau ci\-dessous.  
  
### Conditions d'erreur  
  
|`buffer`|`numberOfElements`|`tm`|Return|Valeur dans `buffer`|  
|--------------|------------------------|----------|------------|--------------------------|  
|`NULL`|Any|Any|`EINVAL`|Non modifié|  
|Non`NULL` \(pointe vers la mémoire valide\)|0|Any|`EINVAL`|Non modifié|  
|Non `NULL`|0\< size \< 26|Any|`EINVAL`|Chaîne vide|  
|Non `NULL`|\>\= 26|`NULL`|`EINVAL`|Chaîne vide|  
|Non `NULL`|\>\= 26|Structure de temps non valide ou valeurs hors limite pour les composants du temps|`EINVAL`|Chaîne vide|  
  
> [!NOTE]
>  Les conditions d'erreur pour `wasctime_s` sont similaires à `asctime_s` sauf que la limite est mesurée en mots.  
  
## Notes  
 La fonction `asctime` convertit une heure enregistrée comme structure en une chaîne de caractères.  La valeur `_tm` est généralement obtenue à partir d'un appel à `gmtime` ou à `localtime`.  Les deux fonctions peuvent être utilisées pour remplir une structure `tm`, comme défini dans TIME.H.  
  
|membre de timeptr|Valeur|  
|-----------------------|------------|  
|`tm_hour`|les heures depuis minuit \(0\-23\)|  
|`tm_isdst`|Positive si l'heure d'été est appliquée ; 0 si l'heure d'été n'est pas appliquée ; négatif si l'état d'heure d'été est inconnu.  La bibliothèque Runtime C suppose l'utilisation des règles des États\-Unis pour implémenter le calcul de l'heure d'été \(DST\).|  
|`tm_mday`|Le jour du mois \(1\-31\)|  
|`tm_min`|Les minutes après les heure \(0\-59\)|  
|`tm_mon`|Le mois \(0\-11 ; Janvier \= 0\)|  
|`tm_sec`|Les secondes après les minutes \(0\-59\)|  
|`tm_wday`|Le jour de la semaine \(0\-6 ; Dimanche \= 0\)|  
|`tm_yday`|Le jour de l'année \(0\-365 ; 1er janvier \= 0\)|  
|`tm_year`|L'année \(année en cours moins 1900\)|  
  
 La chaîne de caractères convertie est également paramétrée conformément aux paramètres de fuseau horaire.  Consultez [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md), [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md), ainsi que les fonctions [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md) pour plus d'informations sur la configuration de l'heure locale et la fonction [\_tzset](../../c-runtime-library/reference/tzset.md) pour plus d'informations sur la configuration de l'environnement et des variables globales du fuseau horaire.  
  
 Le résultat de chaîne généré par `asctime_s` contient exactement 26 caractères et se présente sous la forme `Wed Jan 02 02:03:55 1980\n\0`.  Une horloge de 24 heures est utilisé.  Tous les champs ont une largeur constante.  Le nouveau caractère ligne et le caractère null occupent les deux dernières positions de la chaîne.  La valeur passée comme deuxième paramètre doit être au moins aussi grande.  Si elle est inférieure, un code d'erreur, `EINVAL`, est retourné.  
  
 `_wasctime_s` est une version à caractère élargi de `asctime_s`.  `_wasctime_s` et `asctime_s` se comportent sinon de manière identique.  
  
### Mappage de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tasctime_s`|`asctime_s`|`asctime_s`|`_wasctime_s`|  
  
 En C\+\+, l'utilisation de ces fonctions est simplifiée par des surcharges de modèle ; les surcharges peuvent également déduire la longueur de la mémoire tampon automatiquement, en éliminant le besoin de spécifier un argument de taille.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`asctime_s`|\<time.h\>|  
|`_wasctime_s`|\<time.h\> or \<wchar.h\>|  
  
## Sécurité  
 Si le pointeur de mémoire tampon n'est pas `NULL` et le pointeur ne pointe pas vers une mémoire tampon valide, la fonction écrit par dessus, quoi qu'il y ait à l'emplacement.  Cela peut également entraîner une violation d'accès.  
  
 Un [dépassement de mémoire tampon](http://msdn.microsoft.com/library/windows/desktop/ms717795) peut se produire si l'argument de taille transmis est supérieur à la taille réelle de la mémoire tampon.  
  
## Exemple  
 Ce programme place l'heure système dans l'entier long `aclock`, le traduit dans la structure `newtime` puis le convertit au format chaîne pour la sortie, à l'aide de la fonction `asctime_s`.  
  
```  
// crt_asctime_s.c  
#include <time.h>  
#include <stdio.h>  
  
struct tm newtime;  
__time32_t aclock;  
  
int main( void )  
{  
   char buffer[32];  
   errno_t errNum;  
   _time32( &aclock );   // Get time in seconds.  
   _localtime32_s( &newtime, &aclock );   // Convert time to struct tm form.  
  
   // Print local time as a string.  
  
   errNum = asctime_s(buffer, 32, &newtime);  
   if (errNum)  
   {  
       printf("Error code: %d", (int)errNum);  
       return 1;  
   }  
   printf( "Current date and time: %s", buffer );  
   return 0;  
}  
```  
  
  **Date et heure actuelle : Mercredi 14 mai 15:30:17 2003**   
## Équivalent .NET Framework  
  
-   <xref:System.DateTime.ToLongDateString%2A?displayProperty=fullName>  
  
-   <xref:System.DateTime.ToLongTimeString%2A?displayProperty=fullName>  
  
-   <xref:System.DateTime.ToShortDateString%2A?displayProperty=fullName>  
  
-   <xref:System.DateTime.ToShortTimeString%2A?displayProperty=fullName>  
  
-   <xref:System.DateTime.ToString%2A?displayProperty=fullName>  
  
## Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [ctime\_s, \_ctime32\_s, \_ctime64\_s, \_wctime\_s, \_wctime32\_s, \_wctime64\_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [\_tzset](../../c-runtime-library/reference/tzset.md)