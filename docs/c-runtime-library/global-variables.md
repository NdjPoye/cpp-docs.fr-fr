---
title: "Variables globales | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.variables"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "variables globales"
  - "variables globales, bibliothèque runtime Microsoft"
  - "variables, globaux"
ms.assetid: 01d1551c-2f0c-4f72-935c-6442caccf84f
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Variables globales
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La bibliothèque Runtime C Microsoft fournit les variables ou macros globales suivantes.  Plusieurs d'entre elles sont déconseillées au profit de versions fonctionnelles plus sûres, que nous vous recommandons d'utiliser à la place des variables globales.  
  
|Variable|Description|  
|--------------|-----------------|  
|[\_\_argc, \_\_argv, \_\_wargv](../c-runtime-library/argc-argv-wargv.md)|Contient les arguments de ligne de commande.|  
|[\_daylight, \_dstbias, \_timezone, and \_tzname](../c-runtime-library/daylight-dstbias-timezone-and-tzname.md)|Déconseillé.  Utilisez plutôt `_get_daylight`, `_get_dstbias`, `_get_timezone` et `_get_tzname`.<br /><br /> Prend en compte l'heure locale ; utilisé dans certaines fonctions de date et heure.|  
|[errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)|Déconseillé.  Utilisez plutôt `_get_errno`, `_set_errno`, `_get_doserrno`, `_set_doserrno`, `perror` et `strerror`.<br /><br /> Stocke les codes d'erreur et les informations associées.|  
|[\_environ, \_wenviron](../c-runtime-library/environ-wenviron.md)|Déconseillé.  Utilisez plutôt `getenv_s`, `_wgetenv_s`, `_dupenv_s`, `_wdupenv_s`, `_putenv_s` et `_wputenv_s`.<br /><br /> Pointeurs vers des tableaux de pointeurs désignant des chaînes d'environnement de processus ; initialisés au démarrage.|  
|[\_fmode](../c-runtime-library/fmode.md)|Déconseillé.  Utilisez plutôt `_get_fmode` ou `_set_fmode`.<br /><br /> Définit le mode de traduction de fichier par défaut.|  
|[\_iob](../c-runtime-library/iob.md)|Tableau de structures de contrôle d'E\/S pour la console, les fichiers et les appareils.|  
|[\_pctype, \_pwctype, \_wctype, \_mbctype, \_mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)|Contient des informations utilisées par les fonctions de classification des caractères.|  
|[\_pgmptr, \_wpgmptr](../c-runtime-library/pgmptr-wpgmptr.md)|Déconseillé.  Utilisez plutôt `_get_pgmptr` ou `_get_wpgmptr`.<br /><br /> Initialisées au démarrage du programme sur le chemin d'accès complet ou relatif du programme, le nom complet du programme ou le nom du programme sans son extension de nom de fichier, selon la façon dont le programme a été appelé.|  
  
## Voir aussi  
 [Référence sur les bibliothèques Runtime C](../c-runtime-library/c-run-time-library-reference.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)   
 [\_\_argc, \_\_argv, \_\_wargv](../c-runtime-library/argc-argv-wargv.md)   
 [\_get\_daylight](../c-runtime-library/reference/get-daylight.md)   
 [\_get\_dstbias](../c-runtime-library/reference/get-dstbias.md)   
 [\_get\_timezone](../c-runtime-library/reference/get-timezone.md)   
 [\_get\_tzname](../c-runtime-library/reference/get-tzname.md)   
 [perror](../c-runtime-library/reference/perror-wperror.md)   
 [strerror](../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md)   
 [\_get\_doserrno](../c-runtime-library/reference/get-doserrno.md)   
 [\_set\_doserrno](../c-runtime-library/reference/set-doserrno.md)   
 [\_get\_errno](../c-runtime-library/reference/get-errno.md)   
 [\_set\_errno](../c-runtime-library/reference/set-errno.md)   
 [\_dupenv\_s, \_wdupenv\_s](../c-runtime-library/reference/dupenv-s-wdupenv-s.md)   
 [getenv, \_wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)   
 [getenv\_s, \_wgetenv\_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)   
 [\_putenv, \_wputenv](../c-runtime-library/reference/putenv-wputenv.md)   
 [\_putenv\_s, \_wputenv\_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)   
 [\_get\_fmode](../c-runtime-library/reference/get-fmode.md)   
 [\_set\_fmode](../c-runtime-library/reference/set-fmode.md)