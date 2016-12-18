---
title: "_RPT, _RPTF, _RPTW, _RPTFW, macros | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
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
  - "RPT3"
  - "RPTF4"
  - "_RPT4"
  - "RPT1"
  - "_RPTF0"
  - "RPTF3"
  - "_RPTF4"
  - "RPTF1"
  - "RPT4"
  - "_RPT1"
  - "_RPT0"
  - "RPT0"
  - "_RPTF2"
  - "RPTF0"
  - "_RPT3"
  - "_RPT2"
  - "_RPTF3"
  - "RPT2"
  - "_RPTF1"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "déboguer [CRT], utiliser des macros"
  - "_RPTW3 (macro)"
  - "_RPT0 (macro)"
  - "RPTW4 (macro)"
  - "_RPTF3 (macro)"
  - "_RPTW4 (macro)"
  - "RPTF4 (macro)"
  - "RPTFW2 (macro)"
  - "RPTW (macros)"
  - "RPT1 (macro)"
  - "_RPTF (macros)"
  - "RPTFW3 (macro)"
  - "_RPTW0 (macro)"
  - "_RPTF0 (macro)"
  - "macros, déboguer avec"
  - "_RPTW2 (macro)"
  - "RPTF3 (macro)"
  - "RPT3 (macro)"
  - "RPT0 (macro)"
  - "_RPT (macros)"
  - "RPTW3 (macro)"
  - "_RPTFW (macros)"
  - "déboguer les macros pour la création de rapports"
  - "RPTF (macros)"
  - "RPT (macros)"
  - "_RPTW (macros)"
  - "RPTF2 (macro)"
  - "_RPTF1 (macro)"
  - "_RPT1 (macro)"
  - "_RPT4 (macro)"
  - "_RPTFW2 (macro)"
  - "_RPTFW1 (macro)"
  - "RPTF0 (macro)"
  - "_RPT2 (macro)"
  - "RPTFW (macros)"
  - "_RPTW1 (macro)"
  - "_RPTFW0 (macro)"
  - "RPT4 (macro)"
  - "_RPT3 (macro)"
  - "_RPTFW3 (macro)"
  - "_RPTF4 (macro)"
  - "_RPTFW4 (macro)"
  - "_RPTF2 (macro)"
  - "RPTW0 (macro)"
  - "RPTFW4 (macro)"
  - "RPTFW0 (macro)"
  - "RPTW2 (macro)"
  - "RPTF1 (macro)"
  - "RPT2 (macro)"
  - "RPTFW1 (macro)"
  - "RPTW1 (macro)"
ms.assetid: a5bf8b30-57f7-4971-8030-e773b7a1ae13
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _RPT, _RPTF, _RPTW, _RPTFW, macros
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Suit le progrès d'une application en générant un rapport de débogage \(version de débogage uniquement\).  Notez que *n* spécifie le nombre d'arguments dans `args` et peut être 0, 1, 2, 3, 4 ou 5.  
  
## Syntaxe  
  
```  
  
      _RPT  
      n  
      (  
   reportType,  
   format,  
...[args]  
);  
_RPTFn(  
   reportType,  
   format,  
   [args]  
);  
_RPTWn(  
   reportType,  
   format   
   [args]  
);  
_RPTFWn(  
   reportType,  
   format   
   [args]  
);  
```  
  
#### Paramètres  
 `reportType`  
 Type du rapport : `_CRT_WARN`, `_CRT_ERROR`, ou `_CRT_ASSERT`.  
  
 `format`  
 Chaîne de contrôle de format utilisée pour créer le message utilisateur.  
  
 `args`  
 Arguments de substitution utilisés par `format`.  
  
## Notes  
 Toutes ces macros prennent les paramètres `reportType`et `format`.  En outre, ils peuvent également prendre jusqu'à quatre arguments supplémentaires, signifiés par le nombre ajouté au nom de macros.  Par exemple, `_RPT0` et `_RPTF0` ne prennent aucun argument supplémentaire, `_RPT1` et `_RPTF1` prennent `arg1`, `_RPT2` et `_RPTF2` prennent `arg1` et `arg2`, et ainsi de suite.  
  
 Les macros `_RPT` et `_RPTF` sont similaires à la fonction [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md), car elles peuvent être utilisées pour suivre la progression d'une application pendant le processus de débogage.  Toutefois, ces macros sont plus flexibles que `printf` car elles n'ont pas besoin d'être mises entre les instructions `#ifdef` pour les empêcher d'être appelées dans une version commerciale d'une application.  Cette flexibilité est réalisée à l'aide de la macro [\_DEBUG](../../c-runtime-library/debug.md) ; les macros `_RPT` et `_RPTF` sont disponibles uniquement lorsque l'indicateur `_DEBUG` est défini.  Lorsque `_DEBUG` n'est pas défini, les appels à ces macros sont supprimés pendant le prétraitement.  
  
 Les macros `_RPTW` et `_RPTFW` sont des versions à caractères larges de ces macros.  Ils sont similaires à `wprintf` et prennent des chaînes de caractères larges comme arguments.  
  
 Les macros `_RPT` appellent la fonction [\_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) pour générer un rapport de débogage avec un message utilisateur.  Les macros`_RPTW` appellent la fonction `_CrtDbgReportW` pour générer le même rapport avec des caractères larges.  Les macros `_RPTF` et `_RPTFW` créent un rapport de débogage avec le fichier source et le numéro de ligne où la macro de rapport a été appelée, en plus du message utilisateur.  Le message utilisateur est créé en remplaçant les arguments `arg`\[*n*\] dans la chaîne `format`, à l'aide des mêmes règles définies par la fonction [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md).  
  
 `_CrtDbgReport` ou `_CrtDbgReportW` génère le rapport de débogage et détermine ses destinations selon les modes Rapport actuels et le fichier défini pour `reportType`.  Les fonctions [\_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) et [\_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) sont utilisées pour définir les destinations de chaque type de rapport.  
  
 Si une macro `_RPT` est appelée et si ni `_CrtSetReportMode` ni `_CrtSetReportFile` n'a été appelé, les messages sont affichés comme suit.  
  
|Rapport type|Destination de sortie|  
|------------------|---------------------------|  
|`_CRT_WARN`|Le texte d'avertissement n'est pas affiché.|  
|`_CRT_ERROR`|Une fenêtre de menu contextuel  Comme si `_CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_WNDW);` avait été spécifié.|  
|`_CRT_ASSERT`|Identique à `_CRT_ERROR`.|  
  
 Lorsque la destination est une fenêtre comportant un message de débogage et que l'utilisateur choisit le bouton **Réessayer**, `_CrtDbgReport` ou `_CrtDbgReportW` retourne 1, ce qui force ces macros à démarrer, pourvu que le déboguage just\-in\-time \(JIT\) soit autorisé.  Pour plus d'informations sur l'utilisation de macros comme mécanisme de gestion d'erreur de débogage, consultez [Utilisation de macros pour la vérification et la création de rapports](../Topic/Macros%20for%20Reporting.md).  
  
 Deux autres macros existent qui génèrent un rapport de débogage.  La macro [\_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) génère un rapport, mais uniquement lorsque l'argument de l'expression donne FALSE.  [\_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) est exactement comme `_ASSERT`, mais inclut l'expression qui a échoué dans le rapport généré.  
  
## Configuration requise  
  
|Macro|En\-tête requis|  
|-----------|---------------------|  
|`_RPT` macros|\<crtdbg.h\>|  
|`_RPTF` macros|\<crtdbg.h\>|  
|`_RPTW` macros|\<crtdbg.h\>|  
|`_RPTFW` macros|\<crtdbg.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Seulement les versions debug des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
 Bien que celles\-ci soient des macros et soient obtenues en incluant Crtdbg.h, l'application doit se lier avec l'une des bibliothèques de débogage car ces macros appellent d'autres fonctions run\-time.  
  
## Exemple  
 Consultez l'exemple dans la rubrique [\_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)