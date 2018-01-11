---
title: fsetpos | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: fsetpos
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords: fsetpos
dev_langs: C++
helpviewer_keywords:
- streams, setting position indicators
- fsetpos function
ms.assetid: 6d19ff48-1a2b-47b3-9f23-ed0a47b5a46e
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 71dbbf3c56f81b4987fcadb3db98be8d82e70fb2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="fsetpos"></a>fsetpos
Définit l’indicateur de position de flux.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int fsetpos(   
   FILE *stream,  
   const fpos_t *pos   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `stream`  
 Pointeur vers la structure `FILE` .  
  
 `pos`  
 Stockage de l’indicateur de position.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, `fsetpos` retourne 0. En cas d’échec, la fonction retourne une valeur différente de zéro et définit `errno` sur une des constantes manifestes suivantes (définies dans ERRNO.H) : `EBADF` (le fichier n’est pas accessible ou l’objet désigné par `stream` n’est pas un fichier valide) ou `EINVAL` (une valeur non valide pour `stream` ou `pos` a été passée). Si un paramètre non valide est passé, ces fonctions appellent le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  
  
 Pour plus d’informations sur ces codes de retour et les autres, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 Le `fsetpos` fonction définit l’indicateur de position de fichier pour `stream` à la valeur de `pos`, qui est obtenu dans un appel antérieur à `fgetpos` contre `stream`. La fonction efface l’indicateur de fin de fichier et annule les effets de [ungetc](../../c-runtime-library/reference/ungetc-ungetwc.md) sur `stream`. Après l’appel à `fsetpos`, l’opération suivante sur `stream` peut être une entrée ou une sortie.  
  
## <a name="requirements"></a>Configuration requise  
  
|Fonction|En-tête requis|  
|--------------|---------------------|  
|`fsetpos`|\<stdio.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple relatif à [fgetpos](../../c-runtime-library/reference/fgetpos.md).  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fgetpos](../../c-runtime-library/reference/fgetpos.md)