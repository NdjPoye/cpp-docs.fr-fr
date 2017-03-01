---
title: _CrtSetReportFile | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 2e97bccf3c9fec12b0856e48aaed53f5c8d84b6a
ms.lasthandoff: 02/24/2017

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
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|En-tête facultatif|  
|-------------|---------------------|---------------------|  
|`_CrtSetReportFile`|\<crtdbg.h>|\<errno.h>|  
  
 La console n'est pas prise en charge dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] . Les handles de flux standard associés à la console (`stdin`, `stdout` et `stderr`) doivent être redirigés pour que les fonctions Runtime C puissent les utiliser dans les applications du [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]. Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
 **Bibliothèques :** uniquement les versions de débogage des [fonctions de bibliothèque CRT](../../c-runtime-library/crt-library-features.md).  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)
