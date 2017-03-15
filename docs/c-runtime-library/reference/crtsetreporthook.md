---
title: _CrtSetReportHook | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtSetReportHook
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
- _CrtSetReportHook
- CrtSetReportHook
dev_langs:
- C++
helpviewer_keywords:
- CrtSetReportHook function
- _CrtSetReportHook function
ms.assetid: 1ae7c64f-8c84-4797-9574-b59f00f7a509
caps.latest.revision: 13
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
ms.openlocfilehash: 0815dc124612d4f7d3acd3df147bbfb4e3a5fda0
ms.lasthandoff: 02/24/2017

---
# <a name="crtsetreporthook"></a>_CrtSetReportHook
Installe une fonction de création de rapports définie par le client en la raccordant au processus de création de rapports de débogage du runtime C (version de débogage uniquement).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
_CRT_REPORT_HOOK _CrtSetReportHook(   
   _CRT_REPORT_HOOK reportHook   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `reportHook`  
 Nouvelle fonction de création de rapports définie par le client à raccorder au processus de création de rapports de débogage du runtime C.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne la fonction de création de rapports précédente définie par le client.  
  
## <a name="remarks"></a>Notes  
 `_CrtSetReportHook` permet à une application d’utiliser sa propre fonction de création de rapports dans le processus de création de rapports de bibliothèque de débogage runtime C. Ainsi, chaque fois que [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) est appelé pour générer un rapport de débogage, la fonction de création de rapports de l’application est appelée en premier. Grâce à cette fonctionnalité, une application peut effectuer des opérations telles que le filtrage des rapports de débogage afin de se concentrer sur des types d’allocation spécifiques ou d’envoyer un rapport à des destinations non disponibles à l’aide de `_CrtDbgReport`. Quand [_DEBUG](../../c-runtime-library/debug.md) n’est pas défini, les appels à `_CrtSetReportHook` sont supprimés durant le prétraitement.  
  
 Pour obtenir une version plus robuste de `_CrtSetReportHook`, consultez [_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md).  
  
 La fonction `_CrtSetReportHook` installe la nouvelle fonction de création de rapports définie par le client spécifiée dans `reportHook` et retourne le raccordement précédent défini par le client. L’exemple suivant montre comment un raccordement de rapport défini par le client doit être prototypé :  
  
```  
int YourReportHook( int reportType, char *message, int *returnValue );  
```  
  
 où `reportType` est le type de rapport de débogage (`_CRT_WARN`, `_CRT_ERROR` ou `_CRT_ASSERT`), `message` le message utilisateur de débogage entièrement assemblé à inclure dans le rapport, et `returnValue` la valeur spécifiée par la fonction de création de rapports définie par le client qui doit être retournée par `_CrtDbgReport`. Pour obtenir une description complète des types de rapports disponibles, consultez la fonction [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md).  
  
 Si la fonction de création de rapports définie par le client gère intégralement le message de débogage sans nécessiter de création de rapports supplémentaires, la fonction doit retourner `TRUE`. Quand la fonction retourne `FALSE`, `_CrtDbgReport` est appelé pour générer le rapport de débogage à l’aide des paramètres actuels pour le type de rapport, le mode et le fichier. En outre, en spécifiant la valeur de retour `_CrtDbgReport` dans `returnValue`, l’application peut également contrôler si une interruption de débogage se produit. Pour obtenir une description complète de la façon dont le rapport de débogage est configuré et généré, consultez `_CrtSetReportMode`, [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) et `_CrtDbgReport`.  
  
 Pour plus d’informations sur l’utilisation d’autres fonctions d’exécution compatibles avec le raccordement et sur l’écriture de vos propres fonctions de raccordement définies par le client, consultez [Écriture de fonctions de raccordement de débogage](/visualstudio/debugger/debug-hook-function-writing).  
  
> [!NOTE]
>  Si votre application est compilée avec `/clr` et que la fonction de création de rapports est appelée une fois que l’application a quitté la procédure principale, le CLR lève une exception si la fonction de création de rapports appelle des fonctions CRT.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_CrtSetReportHook`|\<crtdbg.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Uniquement les versions de débogage des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [_CrtGetReportHook](../../c-runtime-library/reference/crtgetreporthook.md)
