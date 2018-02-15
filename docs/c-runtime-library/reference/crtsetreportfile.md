---
title: _CrtSetReportFile | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _CrtSetReportFile
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
apitype: DLLExport
f1_keywords:
- CrtSetReportFile
- _CrtSetReportFile
dev_langs:
- C++
helpviewer_keywords:
- CrtSetReportFile function
- _CrtSetReportFile function
ms.assetid: 3126537e-511b-44af-9c1c-0605265eabc4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a97e3f856dae60eeae9b96f3d5b422f8a262c68a
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="crtsetreportfile"></a>_CrtSetReportFile
Après avoir utilisé [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) pour spécifier `_CRTDBG_MODE_FILE`, vous pouvez spécifier le handle de fichier pour recevoir le texte du message. `_CrtSetReportFile` est également utilisé par [_CrtDbgReport, _CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) pour spécifier la destination du texte (version de débogage uniquement).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
_HFILE _CrtSetReportFile(   
   int reportType,  
   _HFILE reportFile   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `reportType`  
 Type de rapport : `_CRT_WARN`, `_CRT_ERROR` et `_CRT_ASSERT`.  
  
 `reportFile`  
 Nouveau fichier de rapport pour `reportType`.  
  
## <a name="return-value"></a>Valeur de retour  
 Quand l’opération réussit, `_CrtSetReportFile` retourne le fichier de rapport précédent défini pour le type de rapport spécifié dans `reportType`. Si une valeur non valide est passée pour `reportType`, cette fonction appelle le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, `errno` a la valeur `EINVAL` et la fonction retourne une valeur `_CRTDBG_HFILE_ERROR`. Pour plus d’informations, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 `_CrtSetReportFile` est utilisé avec la fonction [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) pour définir la ou les destinations d’un type de rapport spécifique généré par `_CrtDbgReport`. Quand `_CrtSetReportMode` est appelé pour assigner le mode de création de rapports `_CRTDBG_MODE_FILE` pour un type de rapport spécifique, `_CrtSetReportFile` doit être appelé pour définir le fichier ou flux spécifique à utiliser comme destination. Quand [_DEBUG](../../c-runtime-library/debug.md) n’est pas défini, les appels à `_CrtSetReportFile` sont supprimés durant le prétraitement.  
  
 Le tableau suivant répertorie les options disponibles pour `reportFile` et le comportement résultant de `_CrtDbgReport`. Ces options sont définies sous forme d’indicateurs binaires dans Crtdbg.h.  
  
 `file handle`  
 Handle vers le fichier qui sera la destination des messages. Aucune tentative n’est effectuée pour vérifier la validité du handle. Vous devez ouvrir et fermer le handle vers le fichier. Exemple :  
  
```  
HANDLE hLogFile;  
hLogFile = CreateFile("c:\\log.txt", GENERIC_WRITE,   
   FILE_SHARE_WRITE, NULL, CREATE_ALWAYS,   
   FILE_ATTRIBUTE_NORMAL, NULL);  
_CrtSetReportMode(_CRT_WARN, _CRTDBG_MODE_FILE);  
_CrtSetReportFile(_CRT_WARN, hLogFile);  
  
_RPT0(_CRT_WARN,"file message\n");  
CloseHandle(hLogFile);  
```  
  
 `_CRTDBG_FILE_STDERR`  
 Écrit un message vers `stderr`, qui peut être redirigé comme suit :  
  
```  
freopen( "c:\\log2.txt", "w", stderr);  
_CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_FILE);  
_CrtSetReportFile(_CRT_ERROR, _CRTDBG_FILE_STDERR);  
  
_RPT0(_CRT_ERROR,"1st message\n");  
```  
  
 `_CRTDBG_FILE_STDOUT`  
 Écrit un message vers `stdout`, que vous pouvez rediriger.  
  
 `_CRTDBG_REPORT_FILE`  
 Retourne le mode de rapport actuel.  
  
 Le fichier de rapport utilisé par chaque type de rapport peut être contrôlé séparément. Par exemple, vous pouvez spécifier qu’un `reportType` `_CRT_ERROR` soit consigné dans `stderr`, et qu’un `reportType` `_CRT_ASSERT` soit consigné dans un flux ou handle de fichier défini par l’utilisateur.  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|En-tête facultatif|  
|-------------|---------------------|---------------------|  
|`_CrtSetReportFile`|\<crtdbg.h>|\<errno.h>|  
  
 La console n’est pas pris en charge dans les applications de plateforme Windows universelle (UWP). Les descripteurs de flux standard qui sont associés à la console :`stdin`, `stdout`, et `stderr`, doivent être redirigés avant que les fonctions d’exécution C de les utiliser dans les applications UWP. Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
 **Bibliothèques :** uniquement les versions de débogage des [fonctions de bibliothèque CRT](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)