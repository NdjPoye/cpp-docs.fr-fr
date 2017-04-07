---
title: "Routines de débogage | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.debug
dev_langs:
- C++
helpviewer_keywords:
- debugging [CRT], using macros
- macros, debugging with
- debug routines
- debug macros
- debugging [CRT], run-time routines
ms.assetid: cb4d2664-10f3-42f7-a516-595558075471
caps.latest.revision: 11
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
translationtype: Human Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 41e3f6151dc3bec38cd672deee681c37e090507f
ms.lasthandoff: 03/29/2017

---
# <a name="debug-routines"></a>Routines de débogage
La version Debug de la bibliothèque Runtime C fournit de nombreux services de diagnostic facilitent le débogage des programmes et permettent aux développeurs de :  
  
-   passer directement dans les fonctions d’exécution pendant le débogage ;  
  
-   résoudre les assertions, les erreurs et les exceptions ;  
  
-   suivre les allocations de tas et empêcher les fuites de mémoire ;  
  
-   signaler des messages de débogage à l’utilisateur.  
  
 Pour utiliser ces routines, l’indicateur [_DEBUG](../c-runtime-library/debug.md) doit être défini. Toutes ces routines ne font rien dans une version commerciale d’une application. Pour plus d’informations sur la façon d’utiliser les nouvelles routines de débogage, consultez [Techniques de débogage CRT](/visualstudio/debugger/crt-debugging-techniques).  
  
### <a name="debug-versions-of-the-c-run-time-library-routines"></a>Versions Debug des routines de la bibliothèque Runtime C  
  
|Routine|Utilisation|  
|-------------|---------|  
|[_ASSERT](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)|Évaluer une expression et générer un rapport de débogage lorsque le résultat est FALSE|  
|[_ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)|Semblable à `_ASSERT`, mais inclut l’expression qui a échoué dans le rapport généré|  
|[_CrtCheckMemory](../c-runtime-library/reference/crtcheckmemory.md)|Confirmer l’intégrité des blocs de mémoire alloués sur le tas de débogage|  
|[_CrtDbgBreak](../c-runtime-library/reference/crtdbgbreak.md)|Définir un point d’arrêt|  
|[_CrtDbgReport, _CrtDbgReportW](../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)|Générer un rapport de débogage avec un message de l’utilisateur et envoyer le rapport à trois destinations possibles|  
|[_CrtDoForAllClientObjects](../c-runtime-library/reference/crtdoforallclientobjects.md)|Appeler une fonction fournie par l’application pour tous les types `_CLIENT_BLOCK` sur le tas|  
|[_CrtDumpMemoryLeaks](../c-runtime-library/reference/crtdumpmemoryleaks.md)|Vider tous les blocs de mémoire sur le tas de débogage quand une fuite de mémoire importante s’est produite|  
|[_CrtIsMemoryBlock](../c-runtime-library/reference/crtismemoryblock.md)|Vérifier qu’un bloc de mémoire spécifié se trouve dans le tas local et qu’il a un identificateur de type de bloc de tas de débogage valide|  
|[_CrtIsValidHeapPointer](../c-runtime-library/reference/crtisvalidheappointer.md)|Vérifier qu’un pointeur spécifié se trouve dans le tas local|  
|[_CrtIsValidPointer](../c-runtime-library/reference/crtisvalidpointer.md)|Vérifier qu’une plage de mémoire spécifiée est valide pour la lecture et l’écriture|  
|[_CrtMemCheckpoint](../c-runtime-library/reference/crtmemcheckpoint.md)|Obtenir l’état actuel du tas de débogage et le stocker dans une structure `_CrtMemState` fournie par l’application|  
|[_CrtMemDifference](../c-runtime-library/reference/crtmemdifference.md)|Comparer deux états de mémoire pour déterminer des différences significatives et retourner les résultats|  
|[_CrtMemDumpAllObjectsSince](../c-runtime-library/reference/crtmemdumpallobjectssince.md)|Vider des informations sur des objets du tas depuis un point de contrôle spécifié ou le début de l’exécution du programme|  
|[_CrtMemDumpStatistics](../c-runtime-library/reference/crtmemdumpstatistics.md)|Vider les informations d’en-tête de débogage pour un état de mémoire spécifié dans un format lisible par l’utilisateur|  
|[_CrtReportBlockType](../c-runtime-library/reference/crtreportblocktype.md)|Retourner le type/sous-type de bloc associé à un pointeur de bloc de tas de débogage donné|  
|[_CrtSetAllocHook](../c-runtime-library/reference/crtsetallochook.md)|Installer une fonction d’allocation définie par le client en la raccordant au processus d’allocation de mémoire de débogage du runtime C|  
|[_CrtSetBreakAlloc](../c-runtime-library/reference/crtsetbreakalloc.md)|Définir un point d’arrêt sur un numéro d’ordre d’allocation d’objet spécifié|  
|[_CrtSetDbgFlag](../c-runtime-library/reference/crtsetdbgflag.md)|Récupérer ou modifier l’état de l’indicateur `_crtDbgFlag` pour contrôler le comportement d’allocation du gestionnaire du tas de débogage|  
|[_CrtSetDumpClient](../c-runtime-library/reference/crtsetdumpclient.md)|Installer une fonction définie par l’application qui est appelée chaque fois qu’une fonction de vidage du débogage est appelée pour vider des blocs de mémoire de type `_CLIENT_BLOCK`|  
|[_CrtSetReportFile](../c-runtime-library/reference/crtsetreportfile.md)|Identifier le fichier ou flux que `_CrtDbgReport` doit utiliser en tant que destination d’un type de rapport spécifique|  
|[_CrtSetReportHook](../c-runtime-library/reference/crtsetreporthook.md)|Installer une fonction de création de rapports définie par le client en la raccordant au processus de création de rapports de débogage du runtime C|  
|[_CrtSetReportHook2, _CrtSetReportHookW2](../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md)|Installer ou désinstaller une fonction de création de rapports définie par le client en la raccordant au processus de création de rapports de débogage du runtime C|  
|[_CrtSetReportMode](../c-runtime-library/reference/crtsetreportmode.md)|Spécifier la ou les destinations générales d’un type de rapport spécifique généré par `_CrtDbgReport`|  
|[_RPT&#91;0,1,2,3,4&#93;](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md)|Suivre la progression de l’application en générant un rapport de débogage en appelant `_CrtDbgReport` avec une chaîne de format et un nombre variable d’arguments. Ne fournit aucune information sur le fichier source ou le numéro de ligne.|  
|[_RPTF&#91;0,1,2,3,4&#93;](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md)|Similaire aux macros `_RPTn`, mais fournit le nom du fichier source et le numéro de ligne d’où provient la demande de rapport|  
|[_calloc_dbg](../c-runtime-library/reference/calloc-dbg.md)|Allouer un nombre spécifié de blocs de mémoire dans le tas avec de l’espace supplémentaire pour un en-tête de débogage et des mémoires tampons de remplacement|  
|[_expand_dbg](../c-runtime-library/reference/expand-dbg.md)|Redimensionner un bloc de mémoire spécifié sur le tas l’augmentant ou en le diminuant|  
|[_free_dbg](../c-runtime-library/reference/free-dbg.md)|Libérer un bloc de mémoire sur le tas|  
|[_fullpath_dbg, _wfullpath_dbg](../c-runtime-library/reference/fullpath-dbg-wfullpath-dbg.md)|Créer un nom de chemin absolu ou complet pour le nom de chemin relatif spécifié, en utilisant [_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md) pour allouer de la mémoire|[System::IO::File::Create](https://msdn.microsoft.com/en-us/library/system.io.file.create.aspx)|  
|[_getcwd_dbg, _wgetcwd_dbg](../c-runtime-library/reference/getcwd-dbg-wgetcwd-dbg.md)|Obtenir le répertoire de travail actuel, en utilisant [_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md) pour allouer de la mémoire.|  
|[_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md)|Allouer un bloc de mémoire dans le tas avec de l’espace supplémentaire pour un en-tête de débogage et des mémoires tampons de remplacement|  
|[_msize_dbg](../c-runtime-library/reference/msize-dbg.md)|Calculer la taille d’un bloc de mémoire dans le tas|  
|[_realloc_dbg](../c-runtime-library/reference/realloc-dbg.md)|Réallouer un bloc de mémoire spécifié dans le tas en déplaçant et/ou redimensionnant le bloc|  
|[_strdup_dbg, _wcsdup_dbg](../c-runtime-library/reference/strdup-dbg-wcsdup-dbg.md)|Dupliquer une chaîne, en utilisant [_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md) pour allouer de la mémoire|  
|[_tempnam_dbg, _wtempnam_dbg](../c-runtime-library/reference/tempnam-dbg-wtempnam-dbg.md)|Générer des noms que vous pouvez utiliser pour créer des fichiers temporaires, en utilisant [_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md) pour allouer de la mémoire|  
  
 Les routines de débogage peuvent être utilisées pour parcourir le code source de la plupart des autres routines runtime C pendant le processus de débogage. Cependant, Microsoft considère que certaines technologies sont propriétaires et, par conséquent, ne fournit pas le code source de ces routines. La plupart de ces routines appartiennent à la gestion des exceptions ou aux groupes de traitement à virgule flottante, mais certaines autres sont également incluses. Le tableau suivant répertorie ces routines.  
  
### <a name="c-run-time-routines-that-are-not-available-in-source-code-form"></a>Routines runtime C non disponibles sous forme de code source  
  
||||  
|-|-|-|  
|[acos, acosf, acosl](../c-runtime-library/reference/acos-acosf-acosl.md)|[_fpclass](../c-runtime-library/reference/fpclass-fpclassf.md)|[_nextafter](../c-runtime-library/reference/nextafter-functions.md)|  
|[asin](../c-runtime-library/reference/asin-asinf-asinl.md)|[_fpieee_flt](../c-runtime-library/reference/fpieee-flt.md)|[pow](../c-runtime-library/reference/pow-powf-powl.md)|  
|[atan, atan2](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[_fpreset](../c-runtime-library/reference/fpreset.md)|[printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md), [printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)*|  
|[_cabs](../c-runtime-library/reference/cabs.md)|[frexp](../c-runtime-library/reference/frexp.md)|[_scalb](../c-runtime-library/reference/scalb.md)|  
|[ceil](../c-runtime-library/reference/ceil-ceilf-ceill.md)|[_hypot](../c-runtime-library/reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md)|[scanf, _scanf_l, wscanf, _wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md), [scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)*|  
|[_chgsign, _chgsignf, _chgsignl](../c-runtime-library/reference/chgsign-chgsignf-chgsignl.md)|[_isnan](../c-runtime-library/reference/isnan-isnan-isnanf.md)|[setjmp](../c-runtime-library/reference/setjmp.md)|  
|[_clear87, _clearfp](../c-runtime-library/reference/clear87-clearfp.md)|[_j0](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|[sin](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)|  
|[_control87, _controlfp, \__control87_2](../c-runtime-library/reference/control87-controlfp-control87-2.md)|[_j1](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|[sinh](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)|  
|[copysign, copysignf, copysignl, _copysign, _copysignf, _copysignl](../c-runtime-library/reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md)|[_jn](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|[sqrt](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|  
|[cos](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)|[ldexp](../c-runtime-library/reference/ldexp.md)|[_status87, _statusfp](../c-runtime-library/reference/status87-statusfp-statusfp2.md)|  
|[cosh](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)|[log](../c-runtime-library/reference/log-logf-log10-log10f.md)|[tan](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)|  
|[Exp](../c-runtime-library/reference/exp-expf.md)|[log10](../c-runtime-library/reference/log-logf-log10-log10f.md)|[tanh](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)|  
|[fabs](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|[_logb](../c-runtime-library/reference/logb-logbf-logbl-logb-logbf.md)|[_y0](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|  
|[_finite](../c-runtime-library/reference/finite-finitef.md)|[longjmp](../c-runtime-library/reference/longjmp.md)|[_y1](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|  
|[floor](../c-runtime-library/reference/floor-floorf-floorl.md)|[_matherr](../c-runtime-library/reference/matherr.md)|[_yn](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|  
|[fmod](../c-runtime-library/reference/fmod-fmodf.md)|[modf](../c-runtime-library/reference/modf-modff-modfl.md)||  
  
 \*   Bien que le code source soit disponible pour la majeure partie de cette routine, il effectue un appel interne à une autre routine pour laquelle le code source n’est pas fourni.  
  
 Certaines fonctions de Runtime C et certains opérateurs C++ se comportent différemment quand ils sont appelés à partir d’une version Debug d’une application. (Notez qu’une version Debug d’une application se crée en définissant l’indicateur `_DEBUG` ou en établissant une liaison avec une version Debug de la bibliothèque Runtime C.) Les différences de comportement consistent généralement en des fonctionnalités ou des informations supplémentaires fournies par la routine pour prendre en charge le processus de débogage. Le tableau suivant répertorie ces routines.  
  
### <a name="routines-that-behave-differently-in-a-debug-build-of-an-application"></a>Routines qui se comportent différemment dans une version Debug d’une application  
  
|||  
|-|-|  
|Routine [abort](../c-runtime-library/reference/abort.md) C|Opérateur [delete](../cpp/delete-operator-cpp.md) C++|  
|Routine [assert](../c-runtime-library/reference/assert-macro-assert-wassert.md) C|Opérateur [new](../cpp/new-operator-cpp.md) C++|  
  
## <a name="see-also"></a>Voir aussi  
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)   
 [Vérifications des erreurs au moment de l’exécution](../c-runtime-library/run-time-error-checking.md)
