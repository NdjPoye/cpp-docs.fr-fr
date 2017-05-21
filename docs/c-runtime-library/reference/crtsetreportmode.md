---
title: _CrtSetReportMode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtSetReportMode
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
- _CrtSetReportMode
- CrtSetReportMode
dev_langs:
- C++
helpviewer_keywords:
- _CrtSetReportMode function
- CrtSetReportMode function
ms.assetid: 3ecc6a12-afdd-4242-b046-8187ff6d4b36
caps.latest.revision: 15
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: b7e3cb7562fb63467ef0e0ee28861936fb820fa3
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="crtsetreportmode"></a>_CrtSetReportMode
Spécifie la ou les destinations d’un type de rapport particulier généré par `_CrtDbgReport` et toutes les macros qui appellent [_CrtDbgReport, _CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md), telles que les [macros _ASSERT, _ASSERTE, _ASSERT_EXPR](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), les [macros _ASSERT, _ASSERTE, _ASSERT_EXPR](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), les [macros _RPT, _RPTF, _RPTW, _RPTFW](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) et les [macros _RPT, _RPTF, _RPTW, _RPTFW](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) (version de débogage uniquement).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _CrtSetReportMode(   
   int reportType,  
   int reportMode   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `reportType`  
 Type de rapport : `_CRT_WARN`, `_CRT_ERROR` et `_CRT_ASSERT`.  
  
 `reportMode`  
 Nouveau(x) mode(s) de rapport pour `reportType`.  
  
## <a name="return-value"></a>Valeur de retour  
 Quand l’opération réussit, `_CrtSetReportMode` retourne le(s) mode(s) de rapport précédent(s) pour le type de rapport spécifié dans `reportType`. Si une valeur non valide est passée comme `reportType` ou qu’un mode non valide est spécifié pour `reportMode`, `_CrtSetReportMode` appelle le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, cette fonction affecte à `errno` la valeur `EINVAL` et retourne -1. Pour plus d’informations, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 `_CrtSetReportMode` spécifie la destination de sortie pour `_CrtDbgReport`. Étant donné que les macros `_ASSERT`, `_ASSERTE`, `_RPT` et `_RPTF` appellent `_CrtDbgReport`, `_CrtSetReportMode` spécifie la destination de sortie du texte spécifié avec ces macros.  
  
 Quand [_DEBUG](../../c-runtime-library/debug.md) n’est pas défini, les appels à `_CrtSetReportMode` sont supprimés durant le prétraitement.  
  
 Si vous n’appelez pas `_CrtSetReportMode` pour définir la destination de sortie des messages, les valeurs par défaut suivantes sont appliquées :  
  
-   Les erreurs et les échecs d’assertion sont dirigés vers une fenêtre de message de débogage.  
  
-   Les avertissements émanant des applications Windows sont envoyés à la fenêtre de sortie du débogueur.  
  
-   Les avertissements issus des applications de console ne sont pas affichés.  
  
 Le tableau suivant répertorie les types de rapport définis dans Crtdbg.h.  
  
|Type de rapport|Description|  
|-----------------|-----------------|  
|`_CRT_WARN`|Avertissements, messages et informations qui ne nécessitent pas une attention immédiate.|  
|`_CRT_ERROR`|Erreurs, problèmes irrécupérables et problèmes qui requièrent une attention immédiate.|  
|`_CRT_ASSERT`|Échecs d’assertion (expressions déclarées évaluées à `FALSE`).|  
  
 La fonction `_CrtSetReportMode` assigne le nouveau mode de rapport spécifié dans `reportMode` au type de rapport spécifié dans `reportType` et retourne le mode de rapport défini pour `reportType`. Le tableau suivant répertorie les options disponibles pour `reportMode` et le comportement résultant de `_CrtDbgReport`. Ces options sont définies sous forme d’indicateurs binaires dans Crtdbg.h.  
  
|Mode de rapport|Comportement de _CrtDbgReport|  
|-----------------|-----------------------------|  
|`_CRTDBG_MODE_DEBUG`|Écrit le message dans la fenêtre de sortie du débogueur.|  
|`_CRTDBG_MODE_FILE`|Écrit le message dans un handle de fichier fourni par l’utilisateur. [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) doit être appelée pour définir le flux ou fichier spécifique à utiliser comme destination.|  
|`_CRTDBG_MODE_WNDW`|Crée une boîte de message pour afficher le message avec les boutons `Abort`, `Retry` et `Ignore`.|  
|`_CRTDBG_REPORT_MODE`|Retourne `reportMode` pour le `reportType` spécifié :<br /><br /> 1   `_CRTDBG_MODE_FILE`<br /><br /> 2   `_CRTDBG_MODE_DEBUG`<br /><br /> 4   `_CRTDBG_MODE_WNDW`|  
  
 Chaque type de rapport peut être signalé à l’aide d’un, deux ou trois modes ou sans aucun mode. Ainsi, plusieurs destinations peuvent être définies pour un même type de rapport. Par exemple, le fragment de code suivant envoie les échecs d’assertion à une fenêtre de message de débogage et à `stderr` :  
  
```  
_CrtSetReportMode( _CRT_ASSERT, _CRTDBG_MODE_FILE | _CRTDBG_MODE_WNDW );  
_CrtSetReportFile( _CRT_ASSERT, _CRTDBG_FILE_STDERR );  
```  
  
 En outre, vous pouvez contrôler séparément le(s) mode(s) de création de rapports pour chaque type de rapport. Par exemple, vous pouvez spécifier qu’un `reportType` `_CRT_WARN` soit envoyé à une chaîne de débogage de sortie, et que `_CRT_ASSERT` soit affiché à l’aide d’une fenêtre de message de débogage et envoyé à `stderr`, comme illustré précédemment.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|En-tête facultatif|  
|-------------|---------------------|---------------------|  
|`_CrtSetReportMode`|\<crtdbg.h>|\<errno.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
 **Bibliothèques :** uniquement les versions de débogage des [fonctions de bibliothèque CRT](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)
