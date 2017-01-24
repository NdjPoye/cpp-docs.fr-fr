---
title: "_pclose | Microsoft Docs"
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
  - "_pclose"
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
  - "_pclose"
  - "pclose"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_pclose (fonction)"
  - "pclose (fonction)"
  - "canaux, fermer"
ms.assetid: e2e31a9e-ba3a-4124-bcbb-c4040110b3d3
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _pclose
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Attend un nouvel interpréteur de commandes et ferme le flux sur le canal associé.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
  
      int _pclose(  
FILE *stream   
);  
```  
  
#### Paramètres  
 `stream`  
 Retourne la valeur de l'appel précédent à `_popen`.  
  
## Valeur de retour  
 Retourne l'état de sortie du processeur de commandes se terminant, ou – 1 si une erreur se produit.  Le format de la valeur de retour est identique pour `_cwait`, sauf que les octets de poids faible et de poids fort sont inversés.  Si le flux est **NULL**, `_pclose` définit `errno` à `EINVAL` et retourne \-1.  
  
 Pour plus d'informations sur ces éléments et autres codes d'erreur, consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 La fonction `_pclose` recherche l'ID du processus de l'interpréteur de commandes \(Cmd.exe\) démarré par l'appel associé `_popen`, exécute un appel [\_cwait](../../c-runtime-library/reference/cwait.md) au nouveau interpréteur de commandes, et ferme le flux sur le canal associé.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_pclose`|\<stdio.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Contrôle de processus et d'environnement](../../c-runtime-library/process-and-environment-control.md)   
 [\_pipe](../../c-runtime-library/reference/pipe.md)   
 [\_popen, \_wpopen](../../c-runtime-library/reference/popen-wpopen.md)