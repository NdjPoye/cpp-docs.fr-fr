---
title: _open_osfhandle | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _open_osfhandle
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
- _open_osfhandle
- open_osfhandle
dev_langs:
- C++
helpviewer_keywords:
- open_osfhandle function
- file handles [C++], associating
- _open_osfhandle function
ms.assetid: 30d94df4-7868-4667-a401-9eb67ecb7855
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 8d214df5d1e1cd3a48336723cecbf530402eafe3
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="openosfhandle"></a>_open_osfhandle
Associe un descripteur de fichier Runtime C à un descripteur de fichier de système d’exploitation existant.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      int _open_osfhandle (  
   intptr_t osfhandle,  
   int flags   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `osfhandle`  
 Descripteur de fichier de système d’exploitation.  
  
 `flags`  
 Types d’opération autorisés.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, `_open_osfhandle` retourne un descripteur de fichier Runtime C. Sinon, elle retourne -1.  
  
## <a name="remarks"></a>Remarques  
 La fonction `_open_osfhandle` alloue un descripteur de fichier Runtime C et l’associe au descripteur de fichier de système d’exploitation spécifié par `osfhandle`. L’argument `flags` est une expression d’entier formée à partir d’une ou plusieurs des constantes manifestes définies dans Fcntl.h. Quand plusieurs constantes manifestes sont utilisées pour former l’argument `flags`, les constantes sont combinées avec l’opérateur OR au niveau du bit ( **&#124;** ).  
  
 Fcntl.h définit les constantes manifestes suivantes.  
  
 **_O_APPEND**  
 Positionne un pointeur de fichier à la fin du fichier avant chaque opération d’écriture.  
  
 **_O_RDONLY**  
 Ouvre le fichier pour un accès en lecture uniquement.  
  
 **_O_TEXT**  
 Ouvre le fichier en mode texte (traduit).  
  
 **_O_WTEXT**  
 Ouvre le fichier en mode Unicode (UTF-16 traduit).  
  
 Pour fermer un fichier ouvert avec `_open_osfhandle`, appelez `_close`. Le descripteur sous-jacent étant aussi fermé par un appel à `_close`, il n’est pas nécessaire d’appeler la fonction Win32 `CloseHandle` au niveau du descripteur d’origine.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_open_osfhandle`|\<io.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)
