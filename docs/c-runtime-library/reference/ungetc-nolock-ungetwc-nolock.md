---
title: _ungetc_nolock, _ungetwc_nolock | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _ungetwc_nolock
- _ungetc_nolock
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
- _ungettc_nolock
- ungetwc_nolock
- ungetc_nolock
- _ungetc_nolock
- _ungetwc_nolock
dev_langs:
- C++
helpviewer_keywords:
- _ungettc_nolock function
- _ungetwc_nolock function
- characters, pushing back onto stream
- _ungetc_nolock function
- ungetwc_nolock function
- ungettc_nolock function
- ungetc_nolock function
ms.assetid: aa02d5c2-1be1-46d2-a8c4-b61269e9d465
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 14bd0f51ac01f2e335a5609a0140e30e83977433
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="ungetcnolock-ungetwcnolock"></a>_ungetc_nolock, _ungetwc_nolock

Renvoie un caractère dans le flux via une transmission de type push.

## <a name="syntax"></a>Syntaxe

```C
int _ungetc_nolock(
   int c,
   FILE *stream
);
wint_t _ungetwc_nolock(
   wint_t c,
   FILE *stream
);
```

### <a name="parameters"></a>Paramètres

*c*<br/>
Caractère à renvoyer (transmission push).

*Flux de données*<br/>
Pointeur désignant la structure **FILE**.

## <a name="return-value"></a>Valeur de retour

Si réussite, chacune de ces fonctions retourne l’argument de caractère *c*. Si *c* ne peut pas être déplacées ou si aucun caractère n’a été lu, le flux d’entrée est inchangé et **_ungetc_nolock** retourne ** EOF`; **_ungetwc_nolock` retourne **WEOF**. Si *flux* est **NULL**, **EOF** ou **WEOF** est retourné et **errno** a la valeur  **EINVAL**.

Pour plus d’informations sur ces codes d’erreur et les autres, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Notes

Ces fonctions sont sans verrouillage versions de **ungetc** et **ungetwc**. Les versions avec suffixe **_nolock** sont identiques, à ceci près qu’elles ne sont pas protégées contre les interférences avec d’autres threads. Elles peuvent être plus rapides, car elles n’entraînent pas la surcharge liée au verrouillage des autres threads. Utilisez ces fonctions uniquement dans les contextes thread-safe, tels que les applications à un seul thread ou lorsque la portée appelante gère déjà l'isolation des threads.

### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique

|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ungettc_nolock**|**_ungetc_nolock**|**_ungetc_nolock**|**_ungetwc_nolock**|

## <a name="requirements"></a>Spécifications

|Routine|En-tête requis|
|-------------|---------------------|
|**_ungetc_nolock**|\<stdio.h>|
|**_ungetwc_nolock**|\<stdio.h> ou \<wchar.h>|

Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Voir aussi

[E/S de flux](../../c-runtime-library/stream-i-o.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
