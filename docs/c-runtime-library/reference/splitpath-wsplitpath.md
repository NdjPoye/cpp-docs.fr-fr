---
title: "_splitpath, _wsplitpath | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wsplitpath"
  - "_splitpath"
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
  - "api-ms-win-crt-filesystem-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "wsplitpath"
  - "_splitpath"
  - "splitpath"
  - "_wsplitpath"
  - "_tsplitpath"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_splitpath (fonction)"
  - "_tsplitpath (fonction)"
  - "_wsplitpath (fonction)"
  - "noms de chemin d'accès"
  - "noms de chemins d'accès"
  - "splitpath (fonction)"
  - "tsplitpath (fonction)"
  - "wsplitpath (fonction)"
ms.assetid: 32bd76b5-1385-4ee8-a64c-abcb541cd2e4
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _splitpath, _wsplitpath
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Divise un nom de chemin d'accès en ses composants élémentaires.  Des versions plus sécurisées de ces fonctions sont disponibles; consultez [\_splitpath\_s, \_wsplitpath\_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md).  
  
## Syntaxe  
  
```  
void _splitpath(  
   const char *path,  
   char *drive,  
   char *dir,  
   char *fname,  
   char *ext   
);  
void _wsplitpath(  
   const wchar_t *path,  
   wchar_t *drive,  
   wchar_t *dir,  
   wchar_t *fname,  
   wchar_t *ext   
);  
```  
  
#### Paramètres  
 `path`  
 Chemin d'accès complet.  
  
 `drive`  
 Lettre de lecteur, suivi de deux\-points \(`:`\).  Vous pouvez passer `NULL` pour ce paramètre si vous n'avez pas besoin de la lettre de lecteur.  
  
 `dir`  
 Chemin d'accès au répertoire, invluant la barre oblique finale.  Des barres obliques \( `/`\), les barres obliques inverses \( `\` \), ou les deux peuvent être utilisées.  Vous pouvez passer `NULL` pour ce paramètre si vous n'avez pas besoin du chemin d'accès.  
  
 `fname`  
 Nom du fichier de base \(aucune extension\).  Vous pouvez renvoyer `NULL` pour ce paramètre si vous n'avez pas besoin du nom du fichier.  
  
 `ext`  
 Extension du nom de fichier, y compris le principal point \(`.`\).  Vous pouvez passer `NULL` pour ce paramètre si vous n'avez pas besoin de l'extension du nom de fichier.  
  
## Notes  
 La fonction `_splitpath`divise un chemin d'accès par ses quatre composants.  `_splitpath` gère automatiquement des arguments de chaîne de caractères multi\-octets comme appropriés, en identifiant des séquences de caractères multi\-octets d'après la page de codes multioctets en cours d'utilisation.  `_wsplitpath` est une version à caractères larges de `_splitpath` ; les arguments de `_wsplitpath` sont des chaînes à caractères larges.  Ces fonctions se comportent sinon de façon identique.  
  
 **Note de sécurité** Ces fonctions entraînent un risque potentiel provoqué par un dépassement de mémoire tampon.  Les dépassements de mémoire tampon sont une méthode fréquente d'attaque du système, ce qui provoque une élévation des privilèges injustifiée.  Pour plus d'informations, consultez [Solutions contre les dépassements de mémoire tampon](http://msdn.microsoft.com/library/windows/desktop/ms717795).  Des versions plus sécurisées de ces fonctionnalités sont disponibles ; voir le [\_splitpath\_s, \_wsplitpath\_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tsplitpath`|`_splitpath`|`_splitpath`|`_wsplitpath`|  
  
 Chaque composant du chemin d'accès complet est stockée dans une mémoire tampon distincte ; les constantes explicites `_MAX_DRIVE`, `_MAX_DIR`, `_MAX_FNAME`, et `_MAX_EXT`\(définies dans STDLIB.H\) spécifient la taille maximale autorisée pour chaque composant de fichier.  Les composants des fichiers qui sont de dimensions supérieures aux constantes explicites correspondantes engendrent la corruption des données des segments de mémoires.  
  
 Chaque mémoire tampon doit aussis grande que la constante explicite correspondante pour éviter un dépassement de mémoire tampon potentiel.  
  
 Le tableau suivant répertorie les valeurs des constantes explicites.  
  
|Nom|Valeur|  
|---------|------------|  
|\_MAX\_DRIVE|3|  
|\_MAX\_DIR|256|  
|\_MAX\_FNAME|256|  
|\_MAX\_EXT|256|  
  
 Si le chemin complet ne contient aucun composant \(par exemple, un nom de fichier\), `_splitpath` affecte une chaîne vide à la mémoire tampon correspondante.  
  
 Vous pouvez passer `NULL` à `_splitpath` pour un paramètre autre que `path` lequel vous n'avez pas besoin.  
  
 Si `path` est `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, `errno` est défini comme `EINVAL` et la fonction retourne `EINVAL`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_splitpath`|\<stdlib.h\>|  
|`_wsplitpath`|\<stdlib.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
 Consultez l'exemple sur [\_makepath](../../c-runtime-library/reference/makepath-wmakepath.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)   
 [\_fullpath, \_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [\_makepath, \_wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [\_splitpath\_s, \_wsplitpath\_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)