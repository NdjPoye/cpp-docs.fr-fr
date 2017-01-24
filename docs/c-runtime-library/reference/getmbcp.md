---
title: "_getmbcp | Microsoft Docs"
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
  - "_getmbcp"
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
  - "api-ms-win-crt-locale-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_getmbcp"
  - "getmbcp"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_getmbcp (fonction)"
  - "pages de codes, déterminer celui en cours"
  - "getmbcp (fonction)"
ms.assetid: 2db202d4-5c3d-4871-a0b8-ceb0b79ee7bb
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _getmbcp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Récupère la page de codes actuelle.  
  
## Syntaxe  
  
```  
int _getmbcp( void );  
```  
  
## Valeur de retour  
 Retourne la page de codes multioctets actuelle.  Valeur de retour de 0 indique qu'une page de codes d'octet est en cours de utilisation.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_getmbcp`|\<mbctype.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)