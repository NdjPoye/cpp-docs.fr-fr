---
title: _CrtDbgReport, _CrtDbgReportW | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtDbgReport
- _CrtDbgReportW
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
- CrtDbgReport
- CrtDbgReportW
- _CrtDbgReportW
- _CrtDbgReport
dev_langs: C++
helpviewer_keywords:
- debug reporting
- _CrtDbgReport function
- CrtDbgReport function
- CrtDbgReportW function
- _CrtDbgReportW function
ms.assetid: 6e581fb6-f7fb-4716-9432-f0145d639ecc
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a2f148b031312db10449c6f33c67b94f6e171c5f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="crtdbgreport-crtdbgreportw"></a>_CrtDbgReport, _CrtDbgReportW
Génère un rapport avec un message de débogage et envoie ce rapport vers trois destinations possibles (version de débogage uniquement).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _CrtDbgReport(   
   int reportType,  
   const char *filename,  
   int linenumber,  
   const char *moduleName,  
   const char *format [,  
   argument] ...   
);  
int _CrtDbgReportW(   
   int reportType,  
   const wchar_t *filename,  
   int linenumber,  
   const wchar_t *moduleName,  
   const wchar_t *format [,  
   argument] ...   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `reportType`  
 Type de rapport : `_CRT_WARN`, `_CRT_ERROR` et `_CRT_ASSERT`.  
  
 `filename`  
 Pointeur vers le nom du fichier source où l'assertion/rapport s'est produit ou `NULL`.  
  
 `linenumber`  
 Numéro de ligne dans le fichier source où l'assertion/rapport s'est produit ou `NULL`.  
  
 `moduleName`  
 Pointeur vers le nom du module (.exe ou .dll) où l'assertion ou le rapport s'est produit.  
  
 `format`  
 Pointeur vers la chaîne de contrôle de format utilisée pour créer le message utilisateur.  
  
 `argument`  
 Arguments de substitution facultatifs utilisés par `format`.  
  
## <a name="return-value"></a>Valeur de retour  
 Pour toutes les destinations du rapport, `_CrtDbgReport` et `_CrtDbgReportW` retournent -1 si une erreur se produit et la valeur 0 si aucune erreur. Cependant, quand la destination du rapport est une fenêtre de message de débogage et que l’utilisateur clique sur le bouton **Réessayer**, ces fonctions retournent 1. Si l’utilisateur clique sur le bouton **Abandonner** dans la fenêtre Message de débogage, ces fonctions sont immédiatement abandonnées et ne retournent aucune valeur.  
  
 Les macros de débogage [_RPT, _RPTF](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) appellent `_CrtDbgReport` pour générer leurs rapports de débogage. Les versions à caractères larges de ces macros, ainsi que [_ASSERT&#91;E&#93;](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), `_RPTW n` et `_RPTFW n`, utilisent `_CrtDbgReportW` pour générer leurs rapports de débogage. Quand `_CrtDbgReport` ou `_CrtDbgReportW` retourne 1, ces macros démarrent le débogueur, à condition que le débogage juste-à-temps (JIT) soit activé.  
  
## <a name="remarks"></a>Notes  
 `_CrtDbgReport` et `_CrtDbgReportW` peuvent envoyer le rapport de débogage vers trois destinations différentes : un fichier de rapport de débogage, un moniteur de débogage (le débogueur [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]) ou une fenêtre de message de débogage. Deux fonctions de configuration, [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) et [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md), sont utilisées pour spécifier la ou les destinations de chaque type de rapport. Ces fonctions permettent de contrôler séparément la ou les destinations de chaque type de rapport. Par exemple, il est possible de spécifier qu'un `reportType` de type `_CRT_WARN` sera envoyé uniquement au moniteur de débogage, alors que le `reportType` de type `_CRT_ASSERT` sera envoyé à une fenêtre de message de débogage et à un fichier de rapport défini par l'utilisateur.  
  
 `_CrtDbgReportW` est la version à caractères larges de `_CrtDbgReport`. Tous ses paramètres de sortie et de chaîne se trouvent dans des chaînes à caractères larges ; sinon, il est identique à la version à caractères codés sur un octet.  
  
 `_CrtDbgReport` et `_CrtDbgReportW` créent le message utilisateur pour le rapport de débogage en substituant les arguments `argument`[`n`] de la chaîne `format`, selon les mêmes règles que celles définies par les fonctions `printf` ou `wprintf`. Ces fonctions génèrent ensuite le rapport de débogage et déterminent la ou les destinations, en fonction des modes de rapport actifs et du fichier de rapport défini pour `reportType`. Quand le rapport est envoyé vers une fenêtre de message de débogage, `filename`, `lineNumber` et `moduleName` figurent parmi les informations affichées dans la fenêtre.  
  
 Le tableau suivant répertorie les options disponibles pour le ou les modes de rapport et le fichier de rapport, ainsi que le comportement résultant de `_CrtDbgReport` et `_CrtDbgReportW`. Ces options sont définies sous forme d’indicateurs binaires dans \<crtdbg.h>.  
  
|Mode de rapport|Fichier de rapport|Comportement de `_CrtDbgReport` et `_CrtDbgReportW`|  
|-----------------|-----------------|------------------------------------------------|  
|`_CRTDBG_MODE_DEBUG`|Non applicable|Écrit un message à l’aide de l’API Windows [OutputDebugString](http://msdn.microsoft.com/library/windows/desktop/aa363362.aspx).|  
|`_CRTDBG_MODE_WNDW`|Non applicable|Appelle l’API Windows [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) pour créer une boîte de message et afficher le message avec des boutons **Abandonner**, **Réessayer** et **Ignorer**. Si un utilisateur clique sur **Abandonner**, `_CrtDbgReport` ou `_CrtDbgReport` abandonne immédiatement l’opération. Si un utilisateur clique sur **Réessayer**, la valeur 1 est retournée. Si un utilisateur clique sur **Ignorer**, l’exécution continue, puis `_CrtDbgReport` et `_CrtDbgReportW` retournent 0. Notez que le fait de cliquer sur **Ignorer** alors qu’il existe une condition d’erreur entraîne souvent un « comportement indéfini ».|  
|`_CRTDBG_MODE_FILE`|`__HFILE`|Écrit un message dans le `HANDLE` fourni par l’utilisateur à l’aide de l’API Windows [WriteFile](http://msdn.microsoft.com/library/windows/desktop/aa365747.aspx) et ne vérifie pas la validité du handle de fichier ; l’application est chargée d’ouvrir le fichier de rapport et de passer un handle de fichier valide.|  
|`_CRTDBG_MODE_FILE`|`_CRTDBG_FILE_STDERR`|Écrit un message dans `stderr`.|  
|`_CRTDBG_MODE_FILE`|`_CRTDBG_FILE_STDOUT`|Écrit un message dans `stdout`.|  
  
 Le rapport peut être envoyé à une, deux ou trois destinations ou à aucune. Pour plus d’informations sur la spécification du ou des modes de rapport et du fichier de rapport, consultez les fonctions [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) et [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md). Pour plus d’informations sur l’utilisation des macros de débogage et des fonctions de création de rapports, consultez [Macros pour la création de rapports](/visualstudio/debugger/macros-for-reporting).  
  
 Si votre application a besoin d’une plus grande flexibilité que celle proposée par `_CrtDbgReport` et `_CrtDbgReportW`, vous pouvez écrire votre propre fonction de création de rapports et la raccorder au mécanisme de création de rapports de la bibliothèque Runtime C à l’aide de la fonction [_CrtSetReportHook](../../c-runtime-library/reference/crtsetreporthook.md).  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_CrtDbgReport`|\<crtdbg.h>|  
|`_CrtDbgReportW`|\<crtdbg.h>|  
  
 `_CrtDbgReport` et `_CrtDbgReportW` sont des extensions Microsoft. Pour plus d'informations, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliothèques  
 Uniquement les versions de débogage des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_crtdbgreport.c  
#include <crtdbg.h>  
  
int main(int argc, char *argv[]) {  
#ifdef _DEBUG  
   _CrtDbgReport(_CRT_ASSERT, __FILE__, __LINE__, argv[0], NULL);  
#endif  
}  
```  
  
 Consultez [crt_dbg2](http://msdn.microsoft.com/en-us/21e1346a-6a17-4f57-b275-c76813089167) pour obtenir un exemple de la façon de modifier la fonction de rapport.  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md)   
 [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md)   
 [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [_DEBUG](../../c-runtime-library/debug.md)