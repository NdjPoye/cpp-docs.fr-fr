---
title: "fwide | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fwide"
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
apitype: "DLLExport"
f1_keywords: 
  - "fwide"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fwide (fonction)"
ms.assetid: a4641f5b-d74f-4946-95d5-53a64610d28d
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fwide
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Non implémenté.  
  
## Syntaxe  
  
```  
int fwide(  
   FILE *stream,  
   int mode;  
);  
```  
  
#### Paramètres  
 `stream`  
 Pointeur vers la structure `FILE` \(ignoré\).  
  
 `mode`  
 La nouvelle largeur du flux de données : positif pour le caractère large, négatif pour l'octet, zéro pour laisser inchangé. \(Cette valeur est ignorée.\)  
  
## Valeur de retour  
 Cette fonction retourne actuellement uniquement `mode`.  
  
## Notes  
 La version actuelle de cette fonction n'est pas conforme au standard.  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`fwide`|\<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).