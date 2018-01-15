---
title: assert (macro), _assert, _wassert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- assert
- _assert
- _wassert
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- assert
- _assert
- _wassert
- assert/_wassert
dev_langs: C++
helpviewer_keywords:
- aborting programs
- assert function
- assert macro
ms.assetid: a9ca031a-648b-47a6-bdf1-65fc7399dd40
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5a0fe8083cfc131f7e8b1f2133943a1c91f614a6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="assert-macro-assert-wassert"></a>assert (macro), _assert, _wassert
Évalue une expression et, quand le résultat a la valeur `false`, imprime un message de diagnostic et interrompt le programme.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
assert(   
   expression   
);  
void _assert(  
   char const* message,  
   char const* filename,  
   unsigned line  
);  
void _wassert(  
   wchar_t const* message,  
   wchar_t const* filename,  
   unsigned line  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `expression`  
 Expression scalaire (expressions de pointeur comprises) évaluée à une valeur différente de zéro (`true`) ou égale à zéro (`false`).  
  
 `message`  
 Message à afficher.  
  
 `filename`  
 Nom du fichier source où l’assertion a échoué.  
  
 `line`  
 Numéro de ligne dans le fichier source de l’assertion ayant échoué.  
  
## <a name="remarks"></a>Notes  
 La macro `assert` sert généralement à identifier les erreurs de logique pendant le développement de programme. Vous pouvez l’utiliser pour arrêter l’exécution du programme lorsque des conditions inattendues se produisent en implémentant l’argument `expression` pour qu’il soit évalué à `false` uniquement quand le programme fonctionne correctement. Vous pouvez désactiver les contrôles d’assertion au moment de la compilation en définissant la macro `NDEBUG`. Vous pouvez désactiver la macro `assert` sans modifier vos fichiers source à l’aide de l’option de ligne de commande **/DNDEBUG** . Vous pouvez désactiver la macro `assert` dans votre code source en utilisant une directive `#define NDEBUG` avant que \<assert.h> soit inclus.  
  
 La macro `assert` affiche un message de diagnostic quand `expression` est évalué à `false` (0) et appelle [abort](../../c-runtime-library/reference/abort.md) pour terminer l’exécution du programme. Aucune action n'est effectuée si `expression` a la valeur `true` (différente de zéro). Le message de diagnostic contient l'expression qui a échoué, le nom du fichier source et le numéro de ligne où l'assertion a échoué.  
  
 le message de diagnostic est imprimé en caractères larges. Ainsi, la procédure fonctionne comme prévu même si l'expression contient des caractères Unicode.  
  
 La destination du message de diagnostic dépend du type d'application qui a appelé la routine. Les applications console reçoivent toujours le message via `stderr`. Dans une application Windows, `assert` appelle la fonction Windows [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) pour créer une boîte de message pour afficher le message avec un bouton **OK** . Lorsque l'utilisateur clique sur **OK**, le programme s'interrompt immédiatement.  
  
 Lorsque l'application est liée à une version debug des bibliothèques Runtime, `assert` crée un message avec trois boutons : **Abandonner**, **Réessayer**et **Ignorer**. Si l'utilisateur clique sur **Abandonner**, le programme s'interrompt immédiatement. Si l'utilisateur clique sur **Réessayer**, le débogueur est appelé et l'utilisateur peut déboguer le programme si le débogage juste-à-temps (JIT) est activé. Si l'utilisateur clique sur **Ignorer**, `assert` poursuit son exécution normale en créant la boîte de message avec le bouton **OK** . Notez que lorsque vous cliquez sur **Ignorer** alors qu'une condition d'erreur existe, un comportement non défini peut se produire.  
  
 Pour plus d'informations sur le débogage CRT, consultez [Techniques de débogage CRT](/visualstudio/debugger/crt-debugging-techniques).  
  
 Les fonctions `_assert` et `_wassert` sont des fonctions CRT internes. Elles aident à réduire la quantité de code nécessaire dans vos fichiers objet pour prendre en charge les assertions. Nous vous déconseillons d’appeler ces fonctions directement.  
  
 La macro `assert` est activée dans les versions Release et Debug des bibliothèques Runtime C lorsque `NDEBUG` n’est pas défini. Lorsque `NDEBUG` est défini, la macro est disponible mais n’évalue pas son argument et n’a aucun effet. Lorsqu’elle est activée, la macro `assert` appelle `_wassert` pour son implémentation. D’autres macros d’assertion, [_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) et [_ASSERT_EXPR](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), sont également disponibles, mais elles évaluent seulement les expressions qui leur sont passées quand la macro [_DEBUG](../../c-runtime-library/debug.md) a été définie et quand elles sont dans du code lié à la version Debug des bibliothèques Runtime C.  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`assert`, `_wassert`|\<assert.h>|  
  
 La signature de la fonction `_assert` n’est pas disponible dans un fichier d’en-tête. La signature de la fonction `_wassert` est disponible uniquement lorsque la macro `NDEBUG` n’est pas définie.  
  
## <a name="example"></a>Exemple  
 Dans ce programme, la fonction `analyze_string` utilise la macro `assert` pour tester plusieurs conditions liées à la chaîne et à la longueur. Si l'une des conditions échoue, le programme envoie un message indiquant la cause de l'échec.  
  
```  
// crt_assert.c  
// compile by using: cl /W4 crt_assert.c  
#include <stdio.h>  
#include <assert.h>  
#include <string.h>  
  
void analyze_string( char *string );   // Prototype  
  
int main( void )  
{  
   char  test1[] = "abc", *test2 = NULL, test3[] = "";  
  
   printf ( "Analyzing string '%s'\n", test1 ); fflush( stdout );  
   analyze_string( test1 );  
   printf ( "Analyzing string '%s'\n", test2 ); fflush( stdout );  
   analyze_string( test2 );  
   printf ( "Analyzing string '%s'\n", test3 ); fflush( stdout );  
   analyze_string( test3 );  
}  
  
// Tests a string to see if it is NULL,   
// empty, or longer than 0 characters.  
void analyze_string( char * string )  
{  
   assert( string != NULL );        // Cannot be NULL  
   assert( *string != '\0' );       // Cannot be empty  
   assert( strlen( string ) > 2 );  // Length must exceed 2  
}  
```  
  
 Le programme génère cette sortie :  
  
```Output  
Analyzing string 'abc'  
Analyzing string '(null)'  
Assertion failed: string != NULL, file crt_assert.c, line 25  
```  
  
 Après l’échec d’assertion, en fonction de la version du système d’exploitation et de la bibliothèque Runtime, vous pouvez voir une boîte de message contenant du texte semblable à celui-ci :  
  
```Output  
A problem caused the program to stop working correctly. Windows will close the program and notify you if a solution is available.  
```  
  
 Si un débogueur est installé, sélectionnez le bouton **Déboguer** pour démarrer le débogueur, ou **Fermer le programme** pour quitter.  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion des erreurs](../../c-runtime-library/error-handling-crt.md)   
 [Contrôle de processus et d’environnement](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [raise](../../c-runtime-library/reference/raise.md)   
 [signal](../../c-runtime-library/reference/signal.md)   
 [_ASSERT, _ASSERTE, _ASSERT_EXPR, macros](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)   
 [_DEBUG](../../c-runtime-library/debug.md)