---
title: "Versions &#224; la s&#233;curit&#233; am&#233;lior&#233;e des fonctions CRT | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "CRT, améliorations de sécurité"
  - "sécurité (CRT)"
  - "sécurité CRT améliorée"
ms.assetid: f87e5a01-4cb2-4379-9e8f-d4693828c55a
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Versions &#224; la s&#233;curit&#233; am&#233;lior&#233;e des fonctions CRT
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Des versions plus sécurisées des routines de bibliothèque Runtime sont disponibles. Pour plus d’informations sur les améliorations de sécurité dans la bibliothèque CRT, consultez [Fonctionnalités de sécurité dans le CRT](../c-runtime-library/security-features-in-the-crt.md).  
  
 **Fonctions sécurisées**  
  
|Fonction de la bibliothèque CRT|Fonction avec sécurité améliorée|Utilisation|  
|-------------------------------------|--------------------------------------|-----------------|  
|[\_access, \_waccess](../c-runtime-library/reference/access-waccess.md)|[\_access\_s, \_waccess\_s](../c-runtime-library/reference/access-s-waccess-s.md)|Déterminer l'autorisation d'accès aux fichiers|  
|[\_alloca](../c-runtime-library/reference/alloca.md)|[\_malloca](../c-runtime-library/reference/malloca.md)|Allouer de la mémoire sur la pile|  
|[asctime, \_wasctime](../c-runtime-library/reference/asctime-wasctime.md)|[asctime\_s, \_wasctime\_s](../c-runtime-library/reference/asctime-s-wasctime-s.md)|Convertir l'heure du type `struct tm` en chaîne de caractères|  
|[bsearch](../c-runtime-library/reference/bsearch.md)|[bsearch\_s](../c-runtime-library/reference/bsearch-s.md)|Effectuer une recherche binaire dans un tableau trié|  
|Fonction obsolète|[\_cgets\_s, \_cgetws\_s](../c-runtime-library/reference/cgets-s-cgetws-s.md)|Obtenir une chaîne de caractères à partir de la console|  
|[\_chsize](../c-runtime-library/reference/chsize.md)|[\_chsize\_s](../c-runtime-library/reference/chsize-s.md)|Changer la taille d’un fichier|  
|[clearerr](../c-runtime-library/reference/clearerr.md)|[clearerr\_s](../c-runtime-library/reference/clearerr-s.md)|Réinitialiser l’indicateur d’erreur pour un flux|  
|[\_control87, \_controlfp, \_\_control87\_2](../c-runtime-library/reference/control87-controlfp-control87-2.md)|[\_controlfp\_s](../c-runtime-library/reference/controlfp-s.md)|Obtenir et définir le mot de commande à virgule flottante|  
|[\_cprintf, \_cprintf\_l, \_cwprintf, \_cwprintf\_l](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)|[\_cprintf\_s, \_cprintf\_s\_l, \_cwprintf\_s, \_cwprintf\_s\_l](../c-runtime-library/reference/cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)|Mettre en forme et imprimer sur la console|  
|[\_cscanf, \_cscanf\_l, \_cwscanf, \_cwscanf\_l](../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md)|[\_cscanf\_s, \_cscanf\_s\_l, \_cwscanf\_s, \_cwscanf\_s\_l](../c-runtime-library/reference/cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)|Lire des données mises en forme à partir de la console|  
|[ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)|[\_ctime\_s, \_ctime32\_s, \_ctime64\_s, \_wctime\_s, \_wctime32\_s, \_wctime64\_s](../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)|Convertir l'heure du type `time_t`, `__time32_t` ou `__time64_t` en chaîne de caractères|  
|[\_ecvt](../c-runtime-library/reference/ecvt.md)|[\_ecvt\_s](../c-runtime-library/reference/ecvt-s.md)|Convertir un nombre `double` en chaîne|  
|[\_fcvt](../c-runtime-library/reference/fcvt.md)|[\_fcvt\_s](../c-runtime-library/reference/fcvt-s.md)|Convertir un nombre à virgule flottante en chaîne|  
|[fopen, \_wfopen](../c-runtime-library/reference/fopen-wfopen.md)|[fopen\_s, \_wfopen\_s](../c-runtime-library/reference/fopen-s-wfopen-s.md)|Ouvrir un fichier|  
|[fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|[fprintf\_s, \_fprintf\_s\_l, fwprintf\_s, \_fwprintf\_s\_l](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|Imprimer les données mises en forme vers un flux|  
|[fread](../c-runtime-library/reference/fread.md)|[fread\_s](../c-runtime-library/reference/fread-s.md)|Lire depuis un fichier|  
|[\_fread\_nolock](../c-runtime-library/reference/fread-nolock.md)|[\_fread\_nolock\_s](../c-runtime-library/reference/fread-nolock-s2.md)|Lire depuis un fichier sans utiliser un verrou d’écriture multithread|  
|[freopen, \_wfreopen](../c-runtime-library/reference/freopen-wfreopen.md)|[freopen\_s, \_wfreopen\_s](../c-runtime-library/reference/freopen-s-wfreopen-s.md)|Rouvrir le fichier|  
|[fscanf, \_fscanf\_l, fwscanf, \_fwscanf\_l](../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)|[fscanf\_s, \_fscanf\_s\_l, fwscanf\_s, \_fwscanf\_s\_l](../c-runtime-library/reference/fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md)|Lire les données mises en forme d'un flux|  
|[\_ftime, \_ftime32, \_ftime64](../c-runtime-library/reference/ftime-ftime32-ftime64.md)|[\_ftime\_s, \_ftime32\_s, \_ftime64\_s](../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)|Obtenir l'heure actuelle|  
|[\_gcvt](../c-runtime-library/reference/gcvt.md)|[\_gcvt\_s](../c-runtime-library/reference/gcvt-s.md)|Convertir une valeur à virgule flottante en chaîne, et la stocker dans une mémoire tampon|  
|[getenv, \_wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)|[getenv\_s, \_wgetenv\_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)|Obtenir une valeur à partir de l'environnement actuel|  
|Fonction obsolète|[gets\_s, \_getws\_s](../c-runtime-library/reference/gets-s-getws-s.md)|Obtenir une ligne du flux `stdin`|  
|[gmtime, \_gmtime32, \_gmtime64](../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)|[gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)|Convertir une heure de type `time_t` en `struct``tm` ou de type `__time64_t` en `struct tm`|  
|[\_itoa, \_i64toa, \_ui64toa, \_itow, \_i64tow, \_ui64tow](../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md)|[\_itoa\_s, \_i64toa\_s, \_ui64toa\_s, \_itow\_s, \_i64tow\_s, \_ui64tow\_s](../c-runtime-library/reference/itoa-s-i64toa-s-ui64toa-s-itow-s-i64tow-s-ui64tow-s.md)|Convertir un entier en chaîne|  
|[\_lfind](../c-runtime-library/reference/lfind.md)|[\_lfind\_s](../c-runtime-library/reference/lfind-s.md)|Effectuer une recherche linéaire de la clé spécifiée|  
|[localtime, \_localtime32, \_localtime64](../c-runtime-library/reference/localtime-localtime32-localtime64.md)|[localtime\_s, \_localtime32\_s, \_localtime64\_s](../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)|Convertir une heure de type `time_t` en `struct tm` ou de type `__time64_t` en `struct tm` avec une correction locale|  
|[\_lsearch](../c-runtime-library/reference/lsearch.md)|[\_lsearch\_s](../c-runtime-library/reference/lsearch-s.md)|Effectuer une recherche linéaire d’une valeur ; l’ajouter en fin de liste si elle est introuvable|  
|[\_ltoa, \_ltow](../c-runtime-library/reference/ltoa-ltow.md)|[\_ltoa\_s, \_ltow\_s](../c-runtime-library/reference/ltoa-s-ltow-s.md)|Convertir un entier long en chaîne|  
|[\_makepath, \_wmakepath](../c-runtime-library/reference/makepath-wmakepath.md)|[\_makepath\_s, \_wmakepath\_s](../c-runtime-library/reference/makepath-s-wmakepath-s.md)|Créer un nom de chemin d'accès à partir des composants|  
|[\_mbccpy, \_mbccpy\_l](../c-runtime-library/reference/mbccpy-mbccpy-l.md)|[\_mbccpy\_s, \_mbccpy\_s\_l](../c-runtime-library/reference/mbccpy-s-mbccpy-s-l.md)|Copier un caractère multioctet d’une chaîne vers une autre chaîne|  
|[\_mbsnbcat, \_mbsnbcat\_l](../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)|[\_mbsnbcat\_s, \_mbsnbcat\_s\_l](../c-runtime-library/reference/mbsnbcat-s-mbsnbcat-s-l.md)|Ajouter les `n` premiers octets au plus d’une chaîne de caractères multioctets à une autre|  
|[\_mbsnbcpy, \_mbsnbcpy\_l](../c-runtime-library/reference/mbsnbcpy-mbsnbcpy-l.md)|[\_mbsnbcpy\_s, \_mbsnbcpy\_s\_l](../c-runtime-library/reference/mbsnbcpy-s-mbsnbcpy-s-l.md)|Copier `n` octets d’une chaîne vers une chaîne de destination|  
|[\_mbsnbset, \_mbsnbset\_l](../c-runtime-library/reference/mbsnbset-mbsnbset-l.md)|[\_mbsnbset\_s, \_mbsnbset\_s\_l](../c-runtime-library/reference/mbsnbset-s-mbsnbset-s-l.md)|Définir les `n` premiers octets d’une chaîne sur un caractère spécifié|  
|[mbsrtowcs](../c-runtime-library/reference/mbsrtowcs.md)|[mbsrtowcs\_s](../c-runtime-library/reference/mbsrtowcs-s.md)|Convertir une chaîne de caractères multioctets en une chaîne de caractères larges correspondante|  
|[mbstowcs, \_mbstowcs\_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)|[mbstowcs\_s, \_mbstowcs\_s\_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|Convertir une séquence de caractères multioctets en une séquence correspondante de caractères larges|  
|[memcpy, wmemcpy](../c-runtime-library/reference/memcpy-wmemcpy.md)|[memcpy\_s, wmemcpy\_s](../c-runtime-library/reference/memcpy-s-wmemcpy-s.md)|Copier des caractères entre mémoires tampons|  
|[memmove, wmemmove](../c-runtime-library/reference/memmove-wmemmove.md)|[memmove\_s, wmemmove\_s](../c-runtime-library/reference/memmove-s-wmemmove-s.md)|Déplacer une mémoire tampon vers une autre|  
|[\_mktemp, \_wmktemp](../c-runtime-library/reference/mktemp-wmktemp.md)|[\_mktemp\_s, \_wmktemp\_s](../c-runtime-library/reference/mktemp-s-wmktemp-s.md)|Créer un nom de fichier unique|  
|[printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|[printf\_s, \_printf\_s\_l, wprintf\_s, \_wprintf\_s\_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|Imprimer la sortie mise en forme dans le flux de sortie standard|  
|[\_putenv, \_wputenv](../c-runtime-library/reference/putenv-wputenv.md)|[\_putenv\_s, \_wputenv\_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)|Créer, modifier ou supprimer des variables d'environnement|  
|[qsort](../c-runtime-library/reference/qsort.md)|[qsort\_s](../c-runtime-library/reference/qsort-s.md)|Effectuer un tri rapide|  
|[rand](../c-runtime-library/reference/rand.md)|[rand\_s](../c-runtime-library/reference/rand-s.md)|Générer un nombre pseudo\-aléatoire|  
|[scanf, \_scanf\_l, wscanf, \_wscanf\_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)|[scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)|Lire les données mises en forme du flux d'entrée standard|  
|[\_searchenv, \_wsearchenv](../c-runtime-library/reference/searchenv-wsearchenv.md)|[\_searchenv\_s, \_wsearchenv\_s](../c-runtime-library/reference/searchenv-s-wsearchenv-s.md)|Rechercher un fichier en utilisant des chemins d'accès d'environnement|  
|[snprintf, \_snprintf, \_snprintf\_l, \_snwprintf, \_snwprintf\_l](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)|[\_snprintf\_s, \_snprintf\_s\_l, \_snwprintf\_s, \_snwprintf\_s\_l](../c-runtime-library/reference/snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md)|Écrire des données mises en forme dans une chaîne|  
|[\_snscanf, \_snscanf\_l, \_snwscanf, \_snwscanf\_l](../c-runtime-library/reference/snscanf-snscanf-l-snwscanf-snwscanf-l.md)|[\_snscanf\_s, \_snscanf\_s\_l, \_snwscanf\_s, \_snwscanf\_s\_l](../c-runtime-library/reference/snscanf-s-snscanf-s-l-snwscanf-s-snwscanf-s-l.md)|Lire des données mises en forme d'une longueur spécifiée à partir d'une chaîne|  
|[\_sopen, \_wsopen](../c-runtime-library/reference/sopen-wsopen.md)|[\_sopen\_s, \_wsopen\_s](../c-runtime-library/reference/sopen-s-wsopen-s.md)|Ouvrir un fichier pour partage|  
|[\_splitpath, \_wsplitpath](../c-runtime-library/reference/splitpath-wsplitpath.md)|[\_splitpath\_s, \_wsplitpath\_s](../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)|Diviser un nom de chemin d'accès en composants|  
|[sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)|[sprintf\_s, \_sprintf\_s\_l, swprintf\_s, \_swprintf\_s\_l](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|Écrire des données mises en forme dans une chaîne|  
|[sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)|[sscanf\_s, \_sscanf\_s\_l, swscanf\_s, \_swscanf\_s\_l](../c-runtime-library/reference/sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)|Lire des données mises en forme à partir d'une chaîne|  
|[strcat, wcscat, \_mbscat](../c-runtime-library/reference/strcat-wcscat-mbscat.md)|[strcat\_s, wcscat\_s, \_mbscat\_s](../c-runtime-library/reference/strcat-s-wcscat-s-mbscat-s.md)|Ajouter une chaîne|  
|[strcpy, wcscpy, \_mbscpy](../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)|[strcpy\_s, wcscpy\_s, \_mbscpy\_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)|Copier une chaîne|  
|[\_strdate, \_wstrdate](../c-runtime-library/reference/strdate-wstrdate.md)|[\_strdate\_s, \_wstrdate\_s](../c-runtime-library/reference/strdate-s-wstrdate-s.md)|Retourner la date système actuelle sous forme de chaîne|  
|[strerror, \_strerror, \_wcserror, \_\_wcserror](../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md)|[strerror\_s, \_strerror\_s, \_wcserror\_s, \_\_wcserror\_s](../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md)|Obtenir un message d’erreur système \(`strerror`, `_wcserror`\) ou imprimer un message d’erreur fourni par l’utilisateur \(`_strerror`, `__wcserror`\)|  
|[\_strlwr, \_wcslwr, \_mbslwr, \_strlwr\_l, \_wcslwr\_l, \_mbslwr\_l](../c-runtime-library/reference/strlwr-wcslwr-mbslwr-strlwr-l-wcslwr-l-mbslwr-l.md)|[\_strlwr\_s, \_strlwr\_s\_l, \_mbslwr\_s, \_mbslwr\_s\_l, \_wcslwr\_s, \_wcslwr\_s\_l](../c-runtime-library/reference/strlwr-s-strlwr-s-l-mbslwr-s-mbslwr-s-l-wcslwr-s-wcslwr-s-l.md)|Convertir une chaîne en minuscules|  
|[strncat, \_strncat\_l, wcsncat, \_wcsncat\_l, \_mbsncat, \_mbsncat\_l](../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|[strncat\_s, \_strncat\_s\_l, wcsncat\_s, \_wcsncat\_s\_l, \_mbsncat\_s, \_mbsncat\_s\_l](../c-runtime-library/reference/strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)|Ajouter des caractères à une chaîne|  
|[strncpy, \_strncpy\_l, wcsncpy, \_wcsncpy\_l, \_mbsncpy, \_mbsncpy\_l](../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)|[strncpy\_s, \_strncpy\_s\_l, wcsncpy\_s, \_wcsncpy\_s\_l, \_mbsncpy\_s, \_mbsncpy\_s\_l](../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)|Copier les caractères d'une chaîne vers une autre|  
|[\_strnset, \_strnset\_l, \_wcsnset, \_wcsnset\_l, \_mbsnset, \_mbsnset\_l](../c-runtime-library/reference/strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)|[\_strnset\_s, \_strnset\_s\_l, \_wcsnset\_s, \_wcsnset\_s\_l, \_mbsnset\_s, \_mbsnset\_s\_l](../c-runtime-library/reference/strnset-s-strnset-s-l-wcsnset-s-wcsnset-s-l-mbsnset-s-mbsnset-s-l.md)|Définir les n premiers caractères d’une chaîne sur le caractère spécifié|  
|[\_strset, \_strset\_l, \_wcsset, \_wcsset\_l, \_mbsset, \_mbsset\_l](../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)|[\_strset\_s, \_strset\_s\_l, \_wcsset\_s, \_wcsset\_s\_l, \_mbsset\_s, \_mbsset\_s\_l](../c-runtime-library/reference/strset-s-strset-s-l-wcsset-s-wcsset-s-l-mbsset-s-mbsset-s-l.md)|Définir tous les caractères d’une chaîne sur le caractère spécifié|  
|[\_strtime, \_wstrtime](../c-runtime-library/reference/strtime-wstrtime.md)|[\_strtime\_s, \_wstrtime\_s](../c-runtime-library/reference/strtime-s-wstrtime-s.md)|Retourner l'heure système actuelle sous forme de chaîne|  
|[strtok, \_strtok\_l, wcstok, \_wcstok\_l, \_mbstok, \_mbstok\_l](../c-runtime-library/reference/strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md)|[strtok\_s, \_strtok\_s\_l, wcstok\_s, \_wcstok\_s\_l, \_mbstok\_s, \_mbstok\_s\_l](../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md)|Rechercher le jeton suivant dans une chaîne en utilisant les paramètres régionaux actifs ou les paramètres régionaux transmis|  
|[\_strupr, \_strupr\_l, \_mbsupr, \_mbsupr\_l, \_wcsupr\_l, \_wcsupr](../c-runtime-library/reference/strupr-strupr-l-mbsupr-mbsupr-l-wcsupr-l-wcsupr.md)|[\_strupr\_s, \_strupr\_s\_l, \_mbsupr\_s, \_mbsupr\_s\_l, \_wcsupr\_s, \_wcsupr\_s\_l](../c-runtime-library/reference/strupr-s-strupr-s-l-mbsupr-s-mbsupr-s-l-wcsupr-s-wcsupr-s-l.md)|Convertir une chaîne en majuscules|  
|[tmpfile](../c-runtime-library/reference/tmpfile.md)|[tmpfile\_s](../c-runtime-library/reference/tmpfile-s.md)|Créer un fichier temporaire|  
|[\_tempnam, \_wtempnam, tmpnam, \_wtmpnam](../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|[tmpnam\_s, \_wtmpnam\_s](../c-runtime-library/reference/tmpnam-s-wtmpnam-s.md)|Générer des noms que vous pouvez utiliser pour créer des fichiers temporaires|  
|[\_ultoa, \_ultow](../c-runtime-library/reference/ultoa-ultow.md)|[\_ultoa\_s, \_ultow\_s](../c-runtime-library/reference/ultoa-s-ultow-s.md)|Convertir un entier long non signé en chaîne|  
|[\_umask](../c-runtime-library/reference/umask.md)|[\_umask\_s](../c-runtime-library/reference/umask-s.md)|Définir le masque d’autorisation de fichier par défaut|  
|[\_vcprintf, \_vcprintf\_l, \_vcwprintf, \_vcwprintf\_l](../c-runtime-library/reference/vcprintf-vcprintf-l-vcwprintf-vcwprintf-l.md)|[\_vcprintf\_s, \_vcprintf\_s\_l, \_vcwprintf\_s, \_vcwprintf\_s\_l](../c-runtime-library/reference/vcprintf-s-vcprintf-s-l-vcwprintf-s-vcwprintf-s-l.md)|Écrire la sortie mise en forme dans la console en utilisant un pointeur désignant une liste d'arguments|  
|[vfprintf, \_vfprintf\_l, vfwprintf, \_vfwprintf\_l](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|[vfprintf\_s, \_vfprintf\_s\_l, vfwprintf\_s, \_vfwprintf\_s\_l](../c-runtime-library/reference/vfprintf-s-vfprintf-s-l-vfwprintf-s-vfwprintf-s-l.md)|Écrire la sortie mise en forme en utilisant un pointeur désignant une liste d'arguments|  
|[vfscanf, vfwscanf](../c-runtime-library/reference/vfscanf-vfwscanf.md)|[vfscanf\_s, vfwscanf\_s](../c-runtime-library/reference/vfscanf-s-vfwscanf-s.md)|Lire les données mises en forme d'un flux|  
|[vprintf, \_vprintf\_l, vwprintf, \_vwprintf\_l](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)|[vprintf\_s, \_vprintf\_s\_l, vwprintf\_s, \_vwprintf\_s\_l](../c-runtime-library/reference/vprintf-s-vprintf-s-l-vwprintf-s-vwprintf-s-l.md)|Écrire la sortie mise en forme en utilisant un pointeur désignant une liste d'arguments|  
|[vscanf, vwscanf](../c-runtime-library/reference/vscanf-vwscanf.md)|[vscanf\_s, vwscanf\_s](../c-runtime-library/reference/vscanf-s-vwscanf-s.md)|Lire les données mises en forme du flux d'entrée standard|  
|[vsnprintf, \_vsnprintf, \_vsnprintf\_l, \_vsnwprintf, \_vsnwprintf\_l](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md)|[vsnprintf\_s, \_vsnprintf\_s, \_vsnprintf\_s\_l, \_vsnwprintf\_s, \_vsnwprintf\_s\_l](../c-runtime-library/reference/vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md)|Écrire la sortie mise en forme en utilisant un pointeur désignant une liste d'arguments|  
|[vsprintf, \_vsprintf\_l, vswprintf, \_vswprintf\_l, \_\_vswprintf\_l](../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md)|[vsprintf\_s, \_vsprintf\_s\_l, vswprintf\_s, \_vswprintf\_s\_l](../c-runtime-library/reference/vsprintf-s-vsprintf-s-l-vswprintf-s-vswprintf-s-l.md)|Écrire la sortie mise en forme en utilisant un pointeur désignant une liste d'arguments|  
|[vsscanf, vswscanf](../c-runtime-library/reference/vsscanf-vswscanf.md)|[vsscanf\_s, vswscanf\_s](../c-runtime-library/reference/vsscanf-s-vswscanf-s.md)|Lire des données mises en forme à partir d'une chaîne|  
|[wcrtomb](../c-runtime-library/reference/wcrtomb.md)|[wcrtomb\_s](../c-runtime-library/reference/wcrtomb-s.md)|Convertir un caractère large dans sa représentation de caractère multioctet|  
|[wcsrtombs](../c-runtime-library/reference/wcsrtombs.md)|[wcsrtombs\_s](../c-runtime-library/reference/wcsrtombs-s.md)|Convertir une chaîne de caractères larges dans sa représentation de chaîne de caractères multioctets|  
|[wcstombs, \_wcstombs\_l](../c-runtime-library/reference/wcstombs-wcstombs-l.md)|[wcstombs\_s, \_wcstombs\_s\_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)|Convertir une séquence de caractères larges en une séquence correspondante de caractères multioctets|  
|[wctomb, \_wctomb\_l](../c-runtime-library/reference/wctomb-wctomb-l.md)|[wctomb\_s, \_wctomb\_s\_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|Convertir un caractère large en caractère multioctet correspondant|  
  
## Voir aussi  
 [Fonctions de bibliothèque CRT](../c-runtime-library/crt-library-features.md)