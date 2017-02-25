---
title: "Gestion du temps | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.memory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "dates, membres de la bibliothèque runtime"
  - "time, gestion de l’heure"
  - "fonctions de date"
  - "fonctions d’heure"
ms.assetid: 93599220-c011-45d5-978f-12182abfdd2f
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# Gestion du temps
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez ces fonctions pour obtenir l’heure actuelle, et la convertir, la régler et la stocker selon vos besoins. L’heure actuelle est l’heure système.  
  
 Les routines `_ftime`  et `localtime` utilisent la variable d’environnement `TZ`. Si `TZ` n’est pas défini, la bibliothèque runtime tente d’utiliser les informations de fuseau horaire spécifiées par le système d’exploitation. Si ces informations ne sont pas disponibles, ces fonctions utilisent la valeur par défaut PST8PDT. Pour plus d’informations sur `TZ`, consultez [\_tzset](../c-runtime-library/reference/tzset.md) et [\_daylight, timezone et \_tzname](../c-runtime-library/daylight-dstbias-timezone-and-tzname.md).  
  
### Routines de temps  
  
|Fonction|Utilisation|Équivalent .NET Framework|  
|--------------|-----------------|-------------------------------|  
|[asctime, \_wasctime](../c-runtime-library/reference/asctime-wasctime.md), [asctime\_s, \_wasctime\_s](../c-runtime-library/reference/asctime-s-wasctime-s.md)|Convertit une heure du type `struct tm` en chaîne de caractères. Les versions de ces fonctions avec le suffixe `_s` sont plus sécurisées.|[System::DateTime::ToLongDateString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongdatestring.aspx), [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx), [System::DateTime::ToShortDateString](https://msdn.microsoft.com/en-us/library/system.datetime.toshortdatestring.aspx), [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx), [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)|  
|[horloge](../c-runtime-library/reference/clock.md)|Renvoie le temps horloge écoulé pour le processus.|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md), [\_ctime\_s, \_ctime32\_s, \_ctime64\_s, \_wctime\_s, \_wctime32\_s, \_wctime64\_s](../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)|Convertit une heure du type `time_t`, `__time32_t` ou `__time64_t` en chaîne de caractères. Les versions de ces fonctions avec le suffixe `_s` sont plus sécurisées.|[System::DateTime::GetDateTimeFormats](https://msdn.microsoft.com/en-us/library/system.datetime.getdatetimeformats.aspx), [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx), [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx), [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx)|  
|[difftime, \_difftime32, \_difftime64](../c-runtime-library/reference/difftime-difftime32-difftime64.md)|Calcule la différence entre deux heures.|[System::DateTime::Subtract](https://msdn.microsoft.com/en-us/library/system.datetime.subtract.aspx)|  
|[\_ftime, \_ftime32, \_ftime64](../c-runtime-library/reference/ftime-ftime32-ftime64.md),[\_ftime\_s, \_ftime32\_s, \_ftime64\_s](../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)|Stocke l’heure système actuelle dans une variable de type `struct _timeb` ou de type `struct``__timeb64`. Les versions de ces fonctions avec le suffixe `_s` sont plus sécurisées.|[System::DateTime::Now](https://msdn.microsoft.com/en-us/library/system.datetime.now.aspx)|  
|[\_futime, \_futime32, \_futime64](../c-runtime-library/reference/futime-futime32-futime64.md)|Définit l’heure de modification du fichier ouvert.|[System::IO::File::SetLastAccessTime](https://msdn.microsoft.com/en-us/library/system.io.file.setlastaccesstime.aspx), [System::IO::File::SetLastWriteTime](https://msdn.microsoft.com/en-us/library/system.io.file.setlastwritetime.aspx), [System::IO::File::SetCreationTime](https://msdn.microsoft.com/en-us/library/system.io.file.setcreationtime.aspx)|  
|[gmtime, \_gmtime32, \_gmtime64](../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md), [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)|Convertit l’heure du type `time_t` en `struct tm` ou du type `__time64_t` en `struct tm`.Les versions de ces fonctions avec le suffixe `_s` sont plus sécurisées.|[System::DateTime::UtcNow](https://msdn.microsoft.com/en-us/library/system.datetime.utcnow.aspx), [System::DateTime::ToUniversalTime](https://msdn.microsoft.com/en-us/library/system.datetime.touniversaltime.aspx)|  
|[localtime, \_localtime32, \_localtime64](../c-runtime-library/reference/localtime-localtime32-localtime64.md), [localtime\_s, \_localtime32\_s, \_localtime64\_s](../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)|Convertit une heure du type `time_t` en `struct tm` ou du type `__time64_t` en `struct tm` avec une correction locale. Les versions de ces fonctions avec le suffixe `_s` sont plus sécurisées.|[System::DateTime::ToLocalTime](https://msdn.microsoft.com/en-us/library/system.datetime.tolocaltime.aspx)|  
|[\_mkgmtime, \_mkgmtime32, \_mkgmtime64](../c-runtime-library/reference/mkgmtime-mkgmtime32-mkgmtime64.md)|Convertit une heure en valeur de calendrier au format GMT \(heure de Greenwich\).|[System::DateTime::ToUniversalTime](https://msdn.microsoft.com/en-us/library/system.datetime.touniversaltime.aspx)|  
|[mktime, \_mktime32, \_mktime64](../c-runtime-library/reference/mktime-mktime32-mktime64.md)|Convertit une heure en valeur de calendrier.|[System::DateTime::DateTime](Overload:System.DateTime.)|  
|[\_strdate, \_wstrdate](../c-runtime-library/reference/strdate-wstrdate.md), [\_strdate\_s, \_wstrdate\_s](../c-runtime-library/reference/strdate-s-wstrdate-s.md)|Renvoie la date système actuelle sous forme de chaîne. Les versions de ces fonctions avec le suffixe `_s` sont plus sécurisées.|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[strftime, wcsftime, \_strftime\_l, \_wcsftime\_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)|Met en forme la chaîne date\/heure pour une utilisation internationale.|[System::DateTime::ToLongDateString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongdatestring.aspx), [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx), [System::DateTime::ToShortDateString](https://msdn.microsoft.com/en-us/library/system.datetime.toshortdatestring.aspx), [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx), [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)|  
|[\_strtime, \_wstrtime](../c-runtime-library/reference/strtime-wstrtime.md), [\_strtime\_s, \_wstrtime\_s](../c-runtime-library/reference/strtime-s-wstrtime-s.md)|Renvoie l’heure système actuelle sous forme de chaîne. Les versions de ces fonctions avec le suffixe `_s` sont plus sécurisées.|[System::DateTime::ToLongDateString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongdatestring.aspx), [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx), [System::DateTime::ToShortDateString](https://msdn.microsoft.com/en-us/library/system.datetime.toshortdatestring.aspx), [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx), [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)|  
|[time, \_time32, \_time64](../c-runtime-library/reference/time-time32-time64.md)|Obtient l’heure système actuelle en type `time_t`, `__time32_t` ou en type `__time64_t`.|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_tzset](../c-runtime-library/reference/tzset.md)|Définit les variables d’heure externes à partir de la variable d’environnement d’heure `TZ`.|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_utime, \_utime32, \_utime64, \_wutime, \_wutime32, \_wutime64](../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md)|Définit l’heure de modification du fichier spécifié en fonction de l’heure actuelle ou de la valeur d’heure stockée dans la structure.|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
  
> [!NOTE]
>  Dans toutes les versions de Microsoft C\/C\+\+ à l’exception de Microsoft C\/C\+\+ version 7.0, et dans toutes les versions de Visual C\+\+, l’heure actuelle renvoyée par la fonction time correspond au nombre de secondes écoulées depuis le 1er janvier 1970 à minuit. Dans Microsoft C\/C\+\+ version 7.0, l’heure actuelle renvoyée par `time`  est le nombre de secondes écoulées depuis le 31 décembre 1899 à minuit.  
  
> [!NOTE]
>  Dans les versions de [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] et de Microsoft C\/C\+\+ antérieures à Visual C\+\+ 2005, `time_t`  était une valeur `long int`  \(32 bits\) et ne pouvait donc pas être utilisé pour les dates postérieures au 19 janvier 2038 à 3:14:07 \(heure UTC\).`time_t`  est maintenant équivalent à `__time64_t` par défaut, mais définir `_USE_32BIT_TIME_T`  change `time_t`  en `__time32_t` et force de nombreuses fonctions time à appeler les versions qui prennent la valeur `time_t` 32 bits. Pour plus d’informations, consultez la rubrique [Types standard](../c-runtime-library/standard-types.md) et les commentaires dans la documentation sur les fonctions time.  
  
## Voir aussi  
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)