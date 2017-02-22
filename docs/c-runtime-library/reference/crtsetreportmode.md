---
title: "_CrtSetReportMode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtSetReportMode"
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
  - "_CrtSetReportMode"
  - "CrtSetReportMode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CrtSetReportMode (fonction)"
  - "CrtSetReportMode (fonction)"
ms.assetid: 3ecc6a12-afdd-4242-b046-8187ff6d4b36
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _CrtSetReportMode
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie la destination ou les destinations pour un type spécifique de rapport généré par `_CrtDbgReport` et toutes les macros qui appellent [\_CrtDbgReport, \_CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md), [\_ASSERT, \_ASSERTE, \_ASSERT\_EXPR \(macros\)](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), [\_ASSERT, \_ASSERTE, \_ASSERT\_EXPR \(macros\)](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), [\_RPT, \_RPTF, \_RPTW, \_RPTFW, macros](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md), et [\_RPT, \_RPTF, \_RPTW, \_RPTFW, macros](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) \(version Debug uniquement\).  
  
## Syntaxe  
  
```  
int _CrtSetReportMode(   
   int reportType,  
   int reportMode   
);  
```  
  
#### Paramètres  
 `reportType`  
 Type de rapport: `_CRT_WARN`, `_CRT_ERROR`, et `_CRT_ASSERT`.  
  
 `reportMode`  
 Nouveaux mode de Rapport ou modes pour `reportType`.  
  
## Valeur de retour  
 Dans l'achèvement réussi, `_CrtSetReportMode` renvoie le mode Rapport ou les modes précédents pour le type de rapport spécifié dans `reportType`.  Si une valeur valide est passée comme mode `reportType` ou non valide est spécifié pour `reportMode`, `_CrtSetReportMode` appelle le gestionnaire de paramètre non valide comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction définit `errno` à `EINVAL` et retourne \-1.  Pour plus d'informations, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 `_CrtSetReportMode` spécifie la destination de sortie pour `_CrtDbgReport`.  Les macros `_ASSERT`, `_ASSERTE`, `_RPT`, et `_RPTF` appellant `_CrtDbgReport`, `_CrtSetReportMode` spécifie la destination de sortie de texte spécifiée avec ces macros.  
  
 Lorsque [\_DEBUG](../../c-runtime-library/debug.md) n'est pas défini, les appels à `_CrtSetReportMode` sont supprimés pendant le prétraitement.  
  
 Si vous n'appelez pas `_CrtSetReportMode` pour définir la destination de sortie des messages, les valeurs par défaut suivantes sont activées :  
  
-   Les échecs Assert et les erreurs sont dirigées vers une fenêtre de message de débogage.  
  
-   Les avertissements d'applications Windows sont envoyés à la fenêtre Sortie du débogueur.  
  
-   Les avertissements des applications console ne sont pas affichés.  
  
 Le tableau suivant répertorie les types de rapports définis dans Crtdbg.h.  
  
|Rapport type|Description|  
|------------------|-----------------|  
|`_CRT_WARN`|Avertissements, messages, les informations qui n'ont pas besoin d'attention immédiate.|  
|`_CRT_ERROR`|Erreurs, problèmes irrécupérables, et problèmes qui nécessitent une attention immédiate.|  
|`_CRT_ASSERT`|Échecs d'assertion \(expressions affirmées qui correspondent à `FALSE`\).|  
  
 La fonction `_CrtSetReportMode` assigne le nouveau mode Rapport spécifié dans `reportMode` au type de rapport spécifié dans `reportType` et renvoie le mode Rapport précédemment défini pour `reportType`.  Le tableau suivant répertorie les options disponibles pour `reportMode` et le comportement résultant de `_CrtDbgReport`.  Ces options sont définies comme bits indicateurs dans Crtdbg.h.  
  
|Mode Rapport|comportement de \_CrtDbgReport|  
|------------------|------------------------------------|  
|`_CRTDBG_MODE_DEBUG`|Écrit le message dans la fenêtre Sortie du débogueur.|  
|`_CRTDBG_MODE_FILE`|Écrit le message à un handle de fichier fournie par l'utilisateur.  [\_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) doit être appelé pour définir un fichier spécifique ou un flux à utiliser comme destination.|  
|`_CRTDBG_MODE_WNDW`|Crée un message pour afficher le message avec `Abort`, `Retry`, et les boutons `Ignore`.|  
|`_CRTDBG_REPORT_MODE`|Renvoie une `reportMode` pour le `reportType` spécifié:<br /><br /> 1   `_CRTDBG_MODE_FILE`<br /><br /> 2   `_CRTDBG_MODE_DEBUG`<br /><br /> 4   `_CRTDBG_MODE_WNDW`|  
  
 Chaque type de rapport peut être enregistré avec un, deux, ou trois modes ou aucun mode.  Par conséquent, il est possible d'avoir plusieurs destination définie pour un seul type de rapport.  Par exemple, le fragment de code suivant provoque des échecs d'assertion à être envoyés vers une fenêtre de message de débogage et à `stderr`:  
  
```  
_CrtSetReportMode( _CRT_ASSERT, _CRTDBG_MODE_FILE | _CRTDBG_MODE_WNDW );  
_CrtSetReportFile( _CRT_ASSERT, _CRTDBG_FILE_STDERR );  
```  
  
 En outre, le mode de création de rapport ou les modes pour chaque type de rapport peuvent être séparément contrôlés.  Par exemple, il est possible de spécifier que `reportType` de `_CRT_WARN` soit envoyé dans une chaîne de sortie de débogage, tandis que `_CRT_ASSERT` soit affiché dans une fenêtre de message de débogage et envoyé à `stderr`, comme illustré précédemment.  
  
## Configuration requise  
  
|Routine|En\-tête requis|En\-tête facultatif|  
|-------------|---------------------|-------------------------|  
|`_CrtSetReportMode`|\<crtdbg.h\>|\<errno.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
 **Bibliothèques :** Versions Debug de [Fonctions de bibliothèque CRT](../../c-runtime-library/crt-library-features.md) uniquement.  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)