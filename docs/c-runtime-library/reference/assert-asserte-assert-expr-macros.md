---
title: _ASSERT, _ASSERTE, _ASSERT_EXPR, macros | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
- _ASSERTE
- ASSERTE
- _ASSERT
- _ASSERT_EXPR
dev_langs:
- C++
helpviewer_keywords:
- debugging [CRT], using macros
- _ASSERTE macro
- macros, debugging with
- debug reporting macros
- _ASSERT macro
- _ASSERT_EXPR macro
ms.assetid: e98fd2a6-7f5e-4aa8-8fe8-e93490deba36
caps.latest.revision: 27
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 99698cf158118a876a3bb78edaaa52f2b9177d0a
ms.lasthandoff: 02/24/2017

---
# <a name="assert-asserte-assertexpr-macros"></a>_ASSERT, _ASSERTE, _ASSERT_EXPR (macros)
Évaluer une expression et générer un rapport de débogage lorsque le résultat est `False` (version de débogage uniquement).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
_ASSERT_EXPR(  
   booleanExpression,  
   message  
);  
_ASSERT(   
   booleanExpression   
);  
_ASSERTE(   
   booleanExpression   
);  
  
```  
  
#### <a name="parameters"></a>Paramètres  
 `booleanExpression`  
 Expression scalaire (expressions de pointeur comprises) évaluée à une valeur différente de zéro (true) ou égale à zéro (false).  
  
 `message`  
 Large chaîne à afficher dans le cadre du rapport.  
  
## <a name="remarks"></a>Notes  
 Les macros `_ASSERT_EXPR`, `_ASSERT` et `_ASSERTE` offrent un mécanisme propre et simple pour vérifier des hypothèses pendant le processus de débogage d’une application. Elles sont très flexibles, car vous n’avez pas besoin de les placer entre des instructions `#ifdef` pour les empêcher d’être appelées dans une version commerciale d’une application. Cette flexibilité s’obtient grâce à la macro [_DEBUG](../../c-runtime-library/debug.md). `_ASSERT_EXPR`, `_ASSERT` et `_ASSERTE` sont disponibles uniquement quand `_DEBUG` est définie au moment de la compilation. Quand `_DEBUG` n’est pas définie, les appels à ces macros sont supprimés lors du prétraitement.  
  
 `_ASSERT_EXPR`, `_ASSERT` et `_ASSERTE` évaluent leur argument `booleanExpression` et, si le résultat est `false` (0), elles affichent un message de diagnostic et appellent [_CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) pour générer un rapport de débogage. La macro `_ASSERT` affiche un message de diagnostic simple,  `_ASSERTE` inclut une représentation sous forme de chaîne de l’expression qui a échoué dans le message, et `_ASSERT_EXPR` inclut la chaîne `message` dans le message de diagnostic. Ces macros ne font rien lorsque `booleanExpression` a une valeur différente de zéro.  
  
 `_ASSERT_EXPR`, `_ASSERT` et `_ASSERTE` appellent `_CrtDbgReportW`, et toute la sortie est donc en caractères larges. `_ASSERTE` affiche correctement les caractères Unicode dans `booleanExpression`, tandis que `_ASSERT_EXPR` affiche les caractères Unicode dans `message`.  
  
 Étant donné que la macro `_ASSERTE` spécifie l’expression qui a échoué, et que `_ASSERT_EXPR` vous permet de spécifier un message dans le rapport généré, elles permettent aux utilisateurs d’identifier le problème sans faire référence au code source de l’application. Toutefois, l’inconvénient est que chaque `message` affiché par `_ASSERT_EXPR` et chaque expression évaluée par `_ASSERTE` sont inclus dans le fichier de sortie (version de débogage) de votre application sous forme de constante de chaîne. Par conséquent, si un grand nombre d’appels sont effectués à `_ASSERT_EXPR` ou `_ASSERTE`, ces expressions peuvent augmenter considérablement la taille de votre fichier de sortie.  
  
 Sauf indication contraire avec les fonctions [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) et [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) , les messages s’affichent dans une boîte de dialogue contextuelle, ce qui équivaut à définir :  
  
`_CrtSetReportMode(CRT_ASSERT, _CRTDBG_MODE_WNDW);`  
  
 `_CrtDbgReportW` génère le rapport de débogage et détermine sa ou ses destinations, en fonction des modes de rapport actifs et du fichier de rapport défini pour le type de rapport `_CRT_ASSERT`. Par défaut, les erreurs et les échecs d’assertion sont dirigés vers une fenêtre de message de débogage. Les fonctions [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) et [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) servent à définir les destinations de chaque type de rapport.  
  
 Lorsque la destination est une fenêtre de message de débogage et que l’utilisateur clique sur le bouton **Réessayer** , `_CrtDbgReportW` retourne la valeur 1. En conséquence, les macros `_ASSERT_EXPR`, `_ASSERT` et `_ASSERTE` démarrent le débogueur, à condition que le débogage juste-à-temps (JIT) soit activé.  
  
 Pour plus d’informations sur le processus de création de rapports, consultez la fonction [_CrtDbgReport, _CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md). Pour plus d’informations sur la résolution des échecs d’assertion et l’utilisation de ces macros comme mécanisme de gestion des erreurs de débogage, consultez [Utilisation de macros pour la vérification et la création de rapports](/visualstudio/debugger/macros-for-reporting).  
  
 Outre les macros `_ASSERT`, vous pouvez utiliser la macro [assert](../../c-runtime-library/reference/assert-macro-assert-wassert.md) pour vérifier la logique du programme. Cette macro est disponible dans les versions Debug et Release des bibliothèques. Les macros de débogage [_RPT, _RPTF](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) sont également disponibles pour générer un rapport de débogage, mais elles n’évaluent pas d’expression. Les macros `_RPT` génèrent un rapport simple. Les macros `_RPTF` incluent le fichier source et le numéro de la ligne où la macro de rapport a été appelée dans le rapport généré. Des versions à caractères larges de ces macros sont disponibles (`_RPTWn`, `_RPTFWn`). Les versions à caractères larges sont identiques aux versions à caractères étroits, sauf que des chaînes de caractères sont utilisées pour tous les paramètres de chaînes et la sortie.  
  
 Bien que `_ASSERT_EXPR`, `_ASSERT` et `_ASSERTE` soient des macros et qu’elles soient disponibles en incluant \<crtdbg.h>, l’application doit établir une liaison à une version Debug de la bibliothèque Runtime C quand `_DEBUG` est définie, car ces macros appellent d’autres fonctions d’exécution.  
  
## <a name="requirements"></a>Spécifications  
  
|Macro|En-tête requis|  
|-----------|---------------------|  
|`_ASSERT_EXPR`,                  `_ASSERT`, `_ASSERTE`|\<crtdbg.h>|  
  
## <a name="example"></a>Exemple  
 Dans ce programme, des appels sont effectués aux macros `_ASSERT` et `_ASSERTE` pour tester la condition `string1 == string2`. Si la condition échoue, ces macros affichent un message de diagnostic. Le groupe de macros `_RPTn` et `_RPTFn` est également utilisé dans ce programme, comme alternative à la fonction `printf` .  
  
```C  
// crt_ASSERT_macro.c  
// compile with: /D_DEBUG /MTd /Od /Zi /link /verbose:lib /debug  
//  
// This program uses the _ASSERT and _ASSERTE debugging macros.  
//  
  
#include <stdio.h>  
#include <string.h>  
#include <malloc.h>  
#include <crtdbg.h>  
  
int main()  
{  
   char *p1, *p2;  
  
   // The Reporting Mode and File must be specified  
   // before generating a debug report via an assert  
   // or report macro.  
   // This program sends all report types to STDOUT.  
   _CrtSetReportMode(_CRT_WARN, _CRTDBG_MODE_FILE);  
   _CrtSetReportFile(_CRT_WARN, _CRTDBG_FILE_STDOUT);  
   _CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_FILE);  
   _CrtSetReportFile(_CRT_ERROR, _CRTDBG_FILE_STDOUT);  
   _CrtSetReportMode(_CRT_ASSERT, _CRTDBG_MODE_FILE);  
   _CrtSetReportFile(_CRT_ASSERT, _CRTDBG_FILE_STDOUT);  
  
   // Allocate and assign the pointer variables.  
   p1 = (char *)malloc(10);  
   strcpy_s(p1, 10, "I am p1");  
   p2 = (char *)malloc(10);  
   strcpy_s(p2, 10, "I am p2");  
  
   // Use the report macros as a debugging  
   // warning mechanism, similar to printf.  
   // Use the assert macros to check if the   
   // p1 and p2 variables are equivalent.  
   // If the expression fails, _ASSERTE will  
   // include a string representation of the  
   // failed expression in the report.  
   // _ASSERT does not include the  
   // expression in the generated report.  
   _RPT0(_CRT_WARN,  
       "Use the assert macros to evaluate the expression p1 == p2.\n");  
   _RPTF2(_CRT_WARN, "\n Will _ASSERT find '%s' == '%s' ?\n", p1, p2);  
   _ASSERT(p1 == p2);  
  
   _RPTF2(_CRT_WARN, "\n\n Will _ASSERTE find '%s' == '%s' ?\n",  
          p1, p2);  
   _ASSERTE(p1 == p2);  
  
   _RPT2(_CRT_ERROR, "'%s' != '%s'\n", p1, p2);  
  
   free(p2);  
   free(p1);  
  
   return 0;  
}  
```  
  
```Output  
Use the assert macros to evaluate the expression p1 == p2.  
crt_ASSERT_macro.c(54) :   
 Will _ASSERT find 'I am p1' == 'I am p2' ?  
crt_ASSERT_macro.c(55) : Assertion failed!  
crt_ASSERT_macro.c(58) :   
  
 Will _ASSERTE find 'I am p1' == 'I am p2' ?  
crt_ASSERT_macro.c(59) : Assertion failed: p1 == p2  
'I am p1' != 'I am p2'  
```  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 [System::Diagnostics::Debug::Assert](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [assert (macro), _assert, _wassert](../../c-runtime-library/reference/assert-macro-assert-wassert.md)   
 [_RPT, _RPTF, _RPTW, _RPTFW, macros](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md)
