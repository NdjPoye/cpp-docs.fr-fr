---
title: _set_abort_behavior | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _set_abort_behavior
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _set_abort_behavior
- set_abort_behavior
dev_langs:
- C++
helpviewer_keywords:
- aborting programs
- _set_abort_behavior function
- set_abort_behavior function
ms.assetid: 43918766-e4ba-4b1f-80e8-1a4a910cd452
caps.latest.revision: 26
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: edf31ccddfb9ab2eaa6de226ff4ec7eb09869438
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="setabortbehavior"></a>_set_abort_behavior
Spécifie l’action à entreprendre quand un programme s’arrête anormalement.  
  
> [!NOTE]
>  N’utilisez pas la fonction `abort` pour arrêter une application [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)], sauf dans les scénarios de test ou de débogage. Les façons de fermer une application [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] par programmation ou via l’interface utilisateur ne sont pas autorisées d’après les [Critères de certification pour les applications Windows 8](http://go.microsoft.com/fwlink/?LinkId=262889). Pour plus d’informations, consultez [Cycle de vie de l’application (applications du Windows Store)](http://go.microsoft.com/fwlink/?LinkId=262853).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
unsigned int _set_abort_behavior(  
   unsigned int flags,  
   unsigned int mask  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 [in] `flags`  
 Nouvelle valeur des indicateurs `abort`.  
  
 [in] `mask`  
 Masque pour les bits d’indicateurs `abort` à définir.  
  
## <a name="return-value"></a>Valeur de retour  
 Ancienne valeur des indicateurs.  
  
## <a name="remarks"></a>Notes  
 Il existe deux indicateurs `abort` : `_WRITE_ABORT_MSG` et `_CALL_REPORTFAULT`. `_WRITE_ABORT_MSG` détermine si un message texte utile est imprimé quand un programme s’arrête anormalement. Le message indique que l’application a appelé la fonction `abort`. Le comportement par défaut consiste à imprimer le message. S’il est défini, l’indicateur `_CALL_REPORTFAULT` spécifie qu’un vidage sur incident Watson est généré et signalé quand `abort` est appelé. Par défaut, le signalement de vidage sur incident est activé dans les builds non DEBUG.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_set_abort_behavior`|\<stdlib.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
  
```C  
// crt_set_abort_behavior.c  
// compile with: /TC  
#include <stdlib.h>  
  
int main()  
{  
   printf("Suppressing the abort message. If successful, this message"  
          " will be the only output.\n");  
   // Suppress the abort message  
   _set_abort_behavior( 0, _WRITE_ABORT_MSG);  
   abort();  
}  
```  
  
```Output  
Suppressing the abort message. If successful, this message will be the only output.  
```  
  
## <a name="see-also"></a>Voir aussi  
 [abort](../../c-runtime-library/reference/abort.md)
