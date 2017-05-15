---
title: fwrite | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- fwrite
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
f1_keywords:
- fwrite
dev_langs:
- C++
helpviewer_keywords:
- streams, writing data to
- fwrite function
ms.assetid: 7afacf3a-72d7-4a50-ba2e-bea1ab9f4124
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 5f99375d93ab5ae54a34d72f23cd86672a79c318
ms.contentlocale: fr-fr
ms.lasthandoff: 04/01/2017

---
# <a name="fwrite"></a>fwrite
Écrit des données dans un flux.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
size_t fwrite(  
   const void *buffer,  
   size_t size,  
   size_t count,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `buffer`  
 Pointeur vers des données à écrire.  
  
 `size`  
 Taille de l'élément, en octets.  
  
 `count`  
 Nombre maximal d'éléments à écrire.  
  
 `stream`  
 Pointeur vers la structure `FILE` .  
  
## <a name="return-value"></a>Valeur de retour  
 `fwrite` retourne le nombre d'éléments complets réellement écrits, qui peut être inférieur à `count` si une erreur se produit. De même, en cas d'erreur, il est impossible de déterminer l'indicateur de position de fichier. Si `stream` ou `buffer` est un pointeur null ou si un nombre impair d’octets à écrire est spécifié en mode Unicode, la fonction appelle le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, cette fonction affecte à `errno` la valeur `EINVAL` et retourne 0.  
  
## <a name="remarks"></a>Notes  
 La fonction `fwrite` écrit jusqu'aux éléments `count`, chacun d'une longueur `size`, de `buffer` vers la sortie `stream`. Le pointeur de fichier associé à `stream` (le cas échéant) est incrémenté du nombre d'octets réellement écrits. Si `stream` est ouvert en mode texte, chaque saut de ligne est remplacé par un retour chariot - saut de ligne paire. Le remplacement n'a aucun effet sur la valeur de retour.  
  
 Quand `stream` est ouvert en mode de traduction Unicode, par exemple, si `stream` est ouvert en appelant `fopen` et en utilisant un paramètre de mode qui inclut `ccs=UNICODE`, `ccs=UTF-16LE` ou `ccs=UTF-8`, ou si le mode est modifié pour un mode de traduction Unicode en utilisant `_setmode` et un paramètre de mode qui inclut `_O_WTEXT`, `_O_U16TEXT` ou `_O_U8TEXT`, `buffer` est interprété comme un pointeur vers un tableau de `wchar_t` qui contient des données UTF-16. Toute tentative d'écriture d'une quantité impaire d'octets dans ce mode provoque une erreur de validation de paramètre.  
  
 Comme cette fonction verrouille le thread appelant, il est thread-safe. Pour une version sans verrouillage, voir `_fwrite_nolock`.  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête requis|  
|--------------|---------------------|  
|`fwrite`|\<stdio.h>|  
  
 Pour plus d’informations sur la compatibilité, voir consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple relatif à [fread](../../c-runtime-library/reference/fread.md).  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de flux](../../c-runtime-library/stream-i-o.md)   
 [_setmode](../../c-runtime-library/reference/setmode.md)   
 [fread](../../c-runtime-library/reference/fread.md)   
 [_fwrite_nolock](../../c-runtime-library/reference/fwrite-nolock.md)   
 [_write](../../c-runtime-library/reference/write.md)
