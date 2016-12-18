---
title: "_CrtSetReportFile | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtSetReportFile"
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
  - "CrtSetReportFile"
  - "_CrtSetReportFile"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "CrtSetReportFile (fonction)"
  - "_CrtSetReportFile (fonction)"
ms.assetid: 3126537e-511b-44af-9c1c-0605265eabc4
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CrtSetReportFile
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Après avoir utilisé [\_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) pour spécifier `_CRTDBG_MODE_FILE`, spécifiez le handle de fichier pour recevoir le texte du message.  `_CrtSetReportFile` est également utilisée par les [\_CrtDbgReport, \_CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) pour spécifier la destination du texte \(version Debug uniquement\).  
  
## Syntaxe  
  
```  
_HFILE _CrtSetReportFile(   
   int reportType,  
   _HFILE reportFile   
);  
```  
  
#### Paramètres  
 `reportType`  
 Type de rapport: `_CRT_WARN`, `_CRT_ERROR`, et `_CRT_ASSERT`.  
  
 `reportFile`  
 Nouveau fichier de rapport pour `reportType`.  
  
## Valeur de retour  
 Après réussite des opérations, `_CrtSetReportFile` retourne le fichier de rapport précédent défini pour le type de rapport spécifié dans `reportType`.  Si une valeur valide est passée pour `reportType`, cette fonction appelle le gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, `errno` est défini comme `EINVAL` et la fonction retourne `_CRTDBG_HFILE_ERROR`.  Pour plus d'informations, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 `_CrtSetReportFile` est utilisé avec la fonction [\_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) pour définir la destination ou des destinations pour un type spécifique de rapport généré par `_CrtDbgReport`.  Lorsque `_CrtSetReportMode` a été appelé pour assigner `_CRTDBG_MODE_FILE` stockant le mode d'un type spécifique de rapport, `_CrtSetReportFile` doit ensuite être appelé pour définir un fichier spécifique ou un flux à utiliser comme destination.  Lorsque [\_DEBUG](../../c-runtime-library/debug.md) n'est pas défini, les appels à `_CrtSetReportFile` sont supprimés pendant le prétraitement.  
  
 Le tableau suivant répertorie les options disponibles pour `reportFile` et le comportement résultant de `_CrtDbgReport`.  Ces options sont définies comme bits indicateurs dans Crtdbg.h.  
  
 `file handle`  
 Un handle vers le fichier qui sera la destination des messages.  Aucune tentative n'est faite pour vérifier la validité du handle.  Vous devez ouvrir et fermer le handle du fichier.  Par exemple :  
  
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
 Écrit le message à `stderr`, qui peut être redirigé comme suit :  
  
```  
freopen( "c:\\log2.txt", "w", stderr);  
_CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_FILE);  
_CrtSetReportFile(_CRT_ERROR, _CRTDBG_FILE_STDERR);  
  
_RPT0(_CRT_ERROR,"1st message\n");  
```  
  
 `_CRTDBG_FILE_STDOUT`  
 Écrit le message à `stdout`, que vous pouvez rediriger.  
  
 `_CRTDBG_REPORT_FILE`  
 Retourne le mode de rapport actuel.  
  
 Le fichier de rapport utilisé par chaque type de rapport peut être séparément contrôlé.  Par exemple, il est possible de spécifier qu'un `reportType` de `_CRT_ERROR` soit stocké dans `stderr`, tandis qu'un `reportType` de `_CRT_ASSERT` enregistré à un handle de fichier ou un flux défini par l'utilisateur.  
  
## Configuration requise  
  
|Routine|En\-tête requis|En\-tête facultatif|  
|-------------|---------------------|-------------------------|  
|`_CrtSetReportFile`|\<crtdbg.h\>|\<errno.h\>|  
  
 La console n'est pas prise en charge dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] .  Les handles de flux standard associés à la console, `stdin`, `stdout` et `stderr` doivent être redirigés pour que les fonctions runtime C puissent les utiliser dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] .  Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
 **Bibliothèques :** Versions Debug de [Fonctions de bibliothèque CRT](../../c-runtime-library/crt-library-features.md) uniquement.  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)