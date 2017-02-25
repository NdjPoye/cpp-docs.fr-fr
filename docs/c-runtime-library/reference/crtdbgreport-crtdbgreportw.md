---
title: "_CrtDbgReport, _CrtDbgReportW | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtDbgReport"
  - "_CrtDbgReportW"
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
  - "CrtDbgReport"
  - "CrtDbgReportW"
  - "_CrtDbgReportW"
  - "_CrtDbgReport"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rapport de débogage"
  - "_CrtDbgReport (fonction)"
  - "CrtDbgReport (fonction)"
  - "CrtDbgReportW (fonction)"
  - "_CrtDbgReportW (fonction)"
ms.assetid: 6e581fb6-f7fb-4716-9432-f0145d639ecc
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# _CrtDbgReport, _CrtDbgReportW
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

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
 Type de rapport : `_CRT_WARN`, `_CRT_ERROR` et `_CRT_ASSERT`.  
  
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
 Pour toutes les destinations du rapport, `_CrtDbgReport` et `_CrtDbgReportW` retournent –1 si une erreur se produit et 0 si aucune erreur n'est rencontrée. Toutefois, lorsque la destination du rapport est une fenêtre de message de débogage et l’utilisateur clique sur le **Réessayer** bouton, ces fonctions retournent 1. Si l’utilisateur clique sur le **abandonner** bouton dans la fenêtre de Message de débogage, ces fonctions immédiatement abandonner et ne retournent pas de valeur.  
  
 Le [_RPT, _RPTF](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) Déboguer des appels de macros `_CrtDbgReport` pour générer leur débogage rapports. Les versions à caractères larges de ces macros, ainsi que [_ASSERT &#91 ; E &#93 ;](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), `_RPTW``n` et `_RPTFW``n`, utilisez `_CrtDbgReportW` pour générer leur débogage rapports. Quand `_CrtDbgReport` ou `_CrtDbgReportW` retourne 1, ces macros démarrent le débogueur, à condition que le débogage juste-à-temps (JIT) soit activé.  
  
## <a name="remarks"></a>Notes  
 `_CrtDbgReport` et `_CrtDbgReportW` peuvent envoyer le rapport de débogage vers trois destinations différentes : un fichier de rapport de débogage, un moniteur de débogage (le débogueur [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]) ou une fenêtre de message de débogage. Deux fonctions de configuration, [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) et [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md), sont utilisées pour spécifier l’ou les destinations de chaque type de rapport. Ces fonctions permettent de contrôler séparément la ou les destinations de chaque type de rapport. Par exemple, il est possible de spécifier qu'un `reportType` de type `_CRT_WARN` sera envoyé uniquement au moniteur de débogage, alors que le `reportType` de type `_CRT_ASSERT` sera envoyé à une fenêtre de message de débogage et à un fichier de rapport défini par l'utilisateur.  
  
 `_CrtDbgReportW` est la version à caractères larges de `_CrtDbgReport`. Tous ses paramètres de sortie et de chaîne se trouvent dans des chaînes à caractères larges ; sinon, il est identique à la version à caractères codés sur un octet.  
  
 `_CrtDbgReport` et `_CrtDbgReportW` créent le message utilisateur pour le rapport de débogage en substituant les arguments `argument`[`n`] de la chaîne `format`, selon les mêmes règles que celles définies par les fonctions `printf` ou `wprintf`. Ces fonctions génèrent ensuite le rapport de débogage et déterminent la ou les destinations, en fonction des modes de rapport actifs et du fichier de rapport défini pour `reportType`. Quand le rapport est envoyé vers une fenêtre de message de débogage, `filename`, `lineNumber` et `moduleName` figurent parmi les informations affichées dans la fenêtre.  
  
 Le tableau suivant répertorie les options disponibles pour le ou les modes de rapport et le fichier de rapport, ainsi que le comportement résultant de `_CrtDbgReport` et `_CrtDbgReportW`. Ces options sont définies sous forme d'indicateurs binaires dans \<crtdbg.h>.  
  
|Mode de rapport|Fichier de rapport|Comportement de `_CrtDbgReport` et `_CrtDbgReportW`|  
|-----------------|-----------------|------------------------------------------------|  
|`_CRTDBG_MODE_DEBUG`|Non applicable|Écrit un message à l’aide de Windows [OutputDebugString](http://msdn.microsoft.com/library/windows/desktop/aa363362.aspx) API.|  
|`_CRTDBG_MODE_WNDW`|Non applicable|Appelle [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) API pour créer une boîte de message pour afficher le message avec **abandonner**, **Réessayer**, et **Ignorer** boutons. Si un utilisateur clique sur **abandonner**, `_CrtDbgReport` ou `_CrtDbgReport` abandonne immédiatement. Si un utilisateur clique sur **Réessayer**, il renvoie la valeur 1. Si un utilisateur clique sur **Ignorer**, l’exécution se poursuit et `_CrtDbgReport` et `_CrtDbgReportW` retournent 0. Notez qu’un clic sur **Ignorer** lorsqu’une condition d’erreur existe entraîne souvent un « comportement indéfini ».|  
|`_CRTDBG_MODE_FILE`|`__HFILE`|Écrit un message fourni par l’utilisateur `HANDLE`, à l’aide de Windows [WriteFile](http://msdn.microsoft.com/library/windows/desktop/aa365747.aspx) API et ne vérifie pas la validité du handle de fichier, l’application est chargée d’ouvrir le fichier de rapport et de passer un handle de fichier valide.|  
|`_CRTDBG_MODE_FILE`|`_CRTDBG_FILE_STDERR`|Écrit un message dans `stderr`.|  
|`_CRTDBG_MODE_FILE`|`_CRTDBG_FILE_STDOUT`|Écrit un message dans `stdout`.|  
  
 Le rapport peut être envoyé à une, deux ou trois destinations ou à aucune. Pour plus d’informations sur le mode de rapport ou de modes et de fichier de rapport, consultez la [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) et [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) fonctions. Pour plus d’informations sur l’utilisation des macros de débogage et les fonctions de rapport, consultez [Macros pour la création de rapports](../Topic/Macros%20for%20Reporting.md).  
  
 Si votre application a besoin de davantage de flexibilité que celle proposée par `_CrtDbgReport` et `_CrtDbgReportW`, vous pouvez écrire votre propre rapport fonction et le connecter à la bibliothèque Runtime C mécanisme de création de rapports à l’aide de la [_CrtSetReportHook](../../c-runtime-library/reference/crtsetreporthook.md) (fonction).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_CrtDbgReport`|\<crtdbg.h>|  
|`_CrtDbgReportW`|\<crtdbg.h>|  
  
 `_CrtDbgReport` et `_CrtDbgReportW` sont des extensions Microsoft. Pour plus d'informations, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliothèques  
 Les versions Debug de [bibliothèques d’exécution C](../../c-runtime-library/crt-library-features.md) uniquement.  
  
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
  
 Consultez [crt_dbg2](http://msdn.microsoft.com/fr-fr/21e1346a-6a17-4f57-b275-c76813089167) pour obtenir un exemple de modification de la fonction de rapport.  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
  
-   [System::Diagnostics::Debug::Write](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.write.aspx)  
  
-   [System::Diagnostics::Debug::WriteLine](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.writeline.aspx)  
  
-   [System::Diagnostics::Debug::WriteIf](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.writeif.aspx)  
  
-   [System::Diagnostics::Debug::WriteLineIf](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.writelineif.aspx)  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md)   
 [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md)   
 [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [_DEBUG](../../c-runtime-library/debug.md)