---
title: _RPT, _RPTF, _RPTW, _RPTFW Macros | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
- RPT3
- RPTF4
- _RPT4
- RPT1
- _RPTF0
- RPTF3
- _RPTF4
- RPTF1
- RPT4
- _RPT1
- _RPT0
- RPT0
- _RPTF2
- RPTF0
- _RPT3
- _RPT2
- _RPTF3
- RPT2
- _RPTF1
dev_langs:
- C++
helpviewer_keywords:
- debugging [CRT], using macros
- _RPTW3 macro
- _RPT0 macro
- RPTW4 macro
- _RPTF3 macro
- _RPTW4 macro
- RPTF4 macro
- RPTFW2 macro
- RPTW macros
- RPT1 macro
- _RPTF macros
- RPTFW3 macro
- _RPTW0 macro
- _RPTF0 macro
- macros, debugging with
- _RPTW2 macro
- RPTF3 macro
- RPT3 macro
- RPT0 macro
- _RPT macros
- RPTW3 macro
- _RPTFW macros
- debug reporting macros
- RPTF macros
- RPT macros
- _RPTW macros
- RPTF2 macro
- _RPTF1 macro
- _RPT1 macro
- _RPT4 macro
- _RPTFW2 macro
- _RPTFW1 macro
- RPTF0 macro
- _RPT2 macro
- RPTFW macros
- _RPTW1 macro
- _RPTFW0 macro
- RPT4 macro
- _RPT3 macro
- _RPTFW3 macro
- _RPTF4 macro
- _RPTFW4 macro
- _RPTF2 macro
- RPTW0 macro
- RPTFW4 macro
- RPTFW0 macro
- RPTW2 macro
- RPTF1 macro
- RPT2 macro
- RPTFW1 macro
- RPTW1 macro
ms.assetid: a5bf8b30-57f7-4971-8030-e773b7a1ae13
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 43efb76381db85f4f1d601cb6d83dd82074e960a
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="rpt-rptf-rptw-rptfw-macros"></a>_RPT, _RPTF, _RPTW, _RPTFW, macros
Suit la progression d’une application en générant un rapport de débogage (version debug uniquement). Notez que  *n*  Spécifie le nombre d’arguments dans `args` et peut être 0, 1, 2, 3, 4 ou 5.  
  
## <a name="syntax"></a>Syntaxe  
  
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
  
#### <a name="parameters"></a>Paramètres  
 `reportType`  
 Type de rapport : `_CRT_WARN`, `_CRT_ERROR` ou `_CRT_ASSERT`.  
  
 `format`  
 Chaîne de contrôle de format utilisée pour créer le message utilisateur.  
  
 `args`  
 Arguments de substitution utilisés par `format`.  
  
## <a name="remarks"></a>Remarques  
 Toutes ces macros prennent le `reportType` et `format` paramètres. De plus, il peuvent aussi accepter jusqu’à quatre arguments supplémentaires, ce qui est indiqué par le nombre ajouté au nom de la macro. Par exemple, `_RPT0` et `_RPTF0` n’acceptent aucun argument supplémentaire, tandis que `_RPT1` et `_RPTF1` prennent `arg1`, `_RPT2` et `_RPTF2` prend `arg1` et `arg2`, et ainsi de suite.  
  
 Les macros `_RPT` et `_RPTF` sont comparables à la fonction [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) dans le sens où elles permettent de suivre la progression d’une application pendant le processus de débogage. Cependant, ces macros sont plus flexibles que `printf`, car elles n’ont pas besoin d’être incluses dans des instructions `#ifdef` pour éviter qu’elles soient appelées dans la version commerciale d’une application. Cette souplesse est à mettre à l’actif de la macro [_DEBUG](../../c-runtime-library/debug.md) ; les macros `_RPT` et `_RPTF` sont disponibles uniquement quand l’indicateur `_DEBUG` est défini. Quand `_DEBUG` n’est pas définie, les appels à ces macros sont supprimés lors du prétraitement.  
  
 Les macros `_RPTW` et `_RPTFW` sont des versions à caractères larges de ces macros. Ils sont comparables à `wprintf` et acceptent les chaînes de caractères larges en tant qu’arguments.  
  
 Les macros `_RPT` appellent la fonction [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) pour générer un rapport de débogage avec un message utilisateur. Les macros `_RPTW` appellent la fonction `_CrtDbgReportW` pour générer le même rapport avec des caractères larges. Outre le message utilisateur, les macros `_RPTF` et `_RPTFW` créent un rapport de débogage à partir du fichier source et du numéro de ligne où la macro de rapport a été appelée. Le message utilisateur est créé en substituant le `arg`[*n*] arguments dans le `format` chaîne, en utilisant les mêmes règles définies par le [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) (fonction).  
  
 `_CrtDbgReport` ou `_CrtDbgReportW` génère le rapport de débogage et détermine ses destinations en fonction des modes de rapport actifs et du fichier défini pour `reportType`. Les fonctions [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) et [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) servent à définir les destinations de chaque type de rapport.  
  
 Si une macro `_RPT` est appelée et que ni `_CrtSetReportMode` ni `_CrtSetReportFile` n’a été appelée, les messages s’affichent comme suit.  
  
|Type de rapport|Destination de sortie|  
|-----------------|------------------------|  
|`_CRT_WARN`|Le texte d’avertissement ne s’affiche pas.|  
|`_CRT_ERROR`|Fenêtre contextuelle. Comme si `_CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_WNDW);` avait été spécifié.|  
|`_CRT_ASSERT`|Comme pour `_CRT_ERROR`.|  
  
 Quand la destination est une fenêtre de message de débogage et que l’utilisateur choisit le bouton **Réessayer**, `_CrtDbgReport` ou `_CrtDbgReportW` retourne la valeur 1, ce qui amène ces macros à démarrer le débogueur, à condition que le débogage juste-à-temps (JIT) soit activé. Pour plus d’informations sur l’utilisation de ces macros comme mécanisme de gestion des erreurs de débogage, consultez [Utilisation de macros pour la vérification et la création de rapports](/visualstudio/debugger/macros-for-reporting).  
  
 Deux autres macros génèrent un rapport de débogage. La macro [_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) génère un rapport, mais seulement quand l’argument d’expression est évalué à FALSE. [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) est en tout point identique à `_ASSERT`, à ceci près qu’elle inclut l’expression qui a échoué dans le rapport généré.  
  
## <a name="requirements"></a>Spécifications  
  
|Macro|En-tête requis|  
|-----------|---------------------|  
|Macros `_RPT`|\<crtdbg.h>|  
|Macros `_RPTF`|\<crtdbg.h>|  
|Macros `_RPTW`|\<crtdbg.h>|  
|Macros `_RPTFW`|\<crtdbg.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Uniquement les versions de débogage des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
 Bien qu’il s’agisse de macros et qu’elles soient obtenues en incluant Crtdbg.h, l’application doit établir une liaison avec l’une des bibliothèques de débogage, car ces macros appellent d’autres fonctions de runtime.  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple présenté dans la rubrique [_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)
