---
title: "_setmaxstdio | Microsoft Docs"
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
  - "_setmaxstdio"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "setmaxstdio"
  - "_setmaxstdio"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_setmaxstdio (fonction)"
  - "nombre maximum de fichiers ouverts"
  - "fichiers ouverts, maximum"
  - "setmaxstdio (fonction)"
ms.assetid: 9e966875-9ff5-47c4-9b5f-e79e83b70249
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _setmaxstdio
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit un maximum pour le nombre de fichiers ouverts simultanément au niveau `stdio`.  
  
## Syntaxe  
  
```  
int _setmaxstdio(  
   int newmax   
);  
```  
  
#### Paramètres  
 `newmax`  
 Nouveau maximum pour le nombre de fichiers ouverts simultanément au niveau `stdio`.  
  
## Valeur de retour  
 Retourne `newmax` si l'opération réussit ; sinon, –1 .  
  
 Si `newmax` est inférieur à `_IOB_ENTRIES` ou supérieur au nombre maximal de descripteurs disponibles dans le système d'exploitation, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction renvoie \-1 et définit `errno` à la valeur `EINVAL`.  
  
 Pour plus d'informations sur ces éléments et autres codes d'erreur, consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 La fonction `_setmaxstdio` change la valeur maximale du nombre de fichiers qui peuvent être ouverts simultanément au niveau `stdio`.  
  
 Le runtime E\/S C prend maintenant en charge beaucoup plus de fichiers ouverts sur les plateformes Win32 que dans les versions antérieures.  Jusqu'à 2.048 fichiers peuvent être ouverts simultanément sur [lowio de niveau](../../c-runtime-library/low-level-i-o.md) \(autrement dit, ouverts et accessibles au moyen de `_open`, `_read`, `_write`, etc. famille des fonctions d'E\/S\).  Jusqu'à 512 fichiers peuvent être ouverts simultanément sur [stdio level](../../c-runtime-library/stream-i-o.md) \(autrement dit, ouverts et accessibles au moyen de `fopen`, `fgetc`, `fputc`, etc. famille des fonctions d'E\/S\).  La limite de 512 fichiers ouverts au niveau de `stdio` peut être augmentée à 2.048 au moyen de la fonction `_setmaxstdio`.  
  
 Étant donné que des fonctions de niveau `stdio`, telles que `fopen`, sont générées à partir de fonctions `lowio`, la valeur maximale de 2.048 est une limite supérieure difficile pour le même nombre de fichiers ouverts accessibles via la bibliothèque Runtime C.  
  
> [!NOTE]
>  Cette limite supérieure peut être au delà de ce qui est pris en charge par une plateforme et une configuration spécifiques Win32.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_setmaxstdio`|\<stdio.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
 Consultez [\_getmaxstdio](../../c-runtime-library/reference/getmaxstdio.md) pour un exemple de l'utilisation de `_setmaxstdio`.  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)