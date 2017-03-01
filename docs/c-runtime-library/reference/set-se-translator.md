---
title: _set_se_translator | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _set_se_translator
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
- _set_se_translator
- set_se_translator
dev_langs:
- C++
helpviewer_keywords:
- set_se_translator function
- exception handling, changing
- _set_se_translator function
ms.assetid: 280842bc-d72a-468b-a565-2d3db893ae0f
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: d8d43b39c9f71807d68f20cb4873abf96d3f91e8
ms.lasthandoff: 02/24/2017

---
# <a name="setsetranslator"></a>_set_se_translator
Gère les exceptions Win32 (exceptions structurées par C) en tant qu'exceptions typées C++.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
_se_translator_function _set_se_translator(  
   _se_translator_function seTransFunction  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `seTransFunction`  
 Pointeur vers une fonction de traduction d'exceptions structurées C que vous écrivez.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne un pointeur vers la précédente fonction de traduction enregistrée par `_set_se_translator`, afin qu'elle puisse être restaurée plus tard. Si aucune fonction précédente n'a été définie, la valeur de retour peut être utilisée pour restaurer le comportement par défaut ; cette valeur peut être Null.  
  
## <a name="remarks"></a>Notes  
 La fonction `_set_se_translator` permet de gérer les exceptions Win32 (exceptions structurées C) en tant qu'exceptions typées C++. Pour que chaque exception C soit gérée par un gestionnaire `catch` C++, définissez d'abord une classe wrapper d'exceptions C qui peut être utilisée, ou dérivée, pour attribuer un type de classe spécifique à une exception C. Pour utiliser cette classe, installez une fonction de traduction d'exception C personnalisée appelée par le mécanisme de gestion des exceptions interne chaque fois qu'une exception C est levée. Dans votre fonction de traduction, vous pouvez lever n'importe quelle exception typée qui peut être interceptée par un gestionnaire `catch` C++ correspondant.  
  
 Vous devez utiliser [/EHa](../../build/reference/eh-exception-handling-model.md) en même temps que `_set_se_translator`.  
  
 Pour spécifier une fonction de traduction personnalisée, appelez `_set_se_translator` avec le nom de votre fonction de traduction comme argument. La fonction de traduction que vous écrivez est appelée une fois pour chaque appel de fonction sur la pile contenant des blocs `try`. Il n'existe aucune fonction de traduction par défaut.  
  
 Votre fonction de traduction se contente de lever une exception typée C++. Si elle effectue d'autres actions (écrire dans un fichier journal, par exemple), votre programme risque de ne pas se comporter comme prévu, car le nombre de fois où la fonction de traduction est appelée dépend de la plateforme.  
  
 Dans un environnement multithread, les fonctions de traduction sont gérées séparément pour chaque thread. Chaque nouveau thread doit installer sa propre fonction de traduction. Par conséquent, chaque thread est responsable de sa propre gestion de traduction. `_set_se_translator` est spécifique à un thread ; une autre DLL peut installer une fonction de traduction différente.  
  
 La fonction `seTransFunction` que vous écrivez doit être une fonction compilée en code natif (pas compilée avec /clr). Elle doit utiliser un entier non signé et un pointeur vers une structure Win32 `_EXCEPTION_POINTERS` comme arguments. Les arguments sont les valeurs de retour des appels aux fonctions API Win32 `GetExceptionCode` et `GetExceptionInformation`, respectivement.  
  
```  
typedef void (*_se_translator_function)(unsigned int, struct _EXCEPTION_POINTERS* );  
```  
  
 Pour `_set_se_translator`, la liaison dynamique au CRT a des conséquences ; une autre DLL du processus peut appeler `_set_se_translator` et remplacer votre gestionnaire par le sien.  
  
 Lorsque vous utilisez `_set_se_translator` à partir du code managé (code compilé avec /clr) ou du code natif et managé mixte, sachez que le traducteur affecte les exceptions générées en code natif uniquement. Les exceptions managées générées en code managé (par exemple, en déclenchant `System::Exception`) ne sont pas acheminées par le biais de la fonction de traduction. Les exceptions générées en code managé à l'aide de la fonction Win32 `RaiseException` ou provoquées par une exception système telle qu'une exception de division par zéro sont acheminées via le traducteur.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_set_se_translator`|\<eh.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_settrans.cpp  
// compile with: /EHa  
#include <stdio.h>  
#include <windows.h>  
#include <eh.h>  
  
void SEFunc();  
void trans_func( unsigned int, EXCEPTION_POINTERS* );  
  
class SE_Exception  
{  
private:  
    unsigned int nSE;  
public:  
    SE_Exception() {}  
    SE_Exception( unsigned int n ) : nSE( n ) {}  
    ~SE_Exception() {}  
    unsigned int getSeNumber() { return nSE; }  
};  
int main( void )  
{  
    try  
    {  
        _set_se_translator( trans_func );  
        SEFunc();  
    }  
    catch( SE_Exception e )  
    {  
        printf( "Caught a __try exception with SE_Exception.\n" );  
    }  
}  
void SEFunc()  
{  
    __try  
    {  
        int x, y=0;  
        x = 5 / y;  
    }  
    __finally  
    {  
        printf( "In finally\n" );  
    }  
}  
void trans_func( unsigned int u, EXCEPTION_POINTERS* pExp )  
{  
    printf( "In trans_func.\n" );  
    throw SE_Exception();  
}  
```  
  
```Output  
In trans_func.  
In finally  
Caught a __try exception with SE_Exception.  
```  
  
## <a name="example"></a>Exemple  
 Bien que les fonctionnalités fournies par `_set_se_translator` ne soient pas disponibles en code managé, il est possible d'utiliser ce mappage en code natif même si ce code natif se trouve dans une compilation sous le commutateur `/clr`, à condition qu'il soit indiqué à l'aide de `#pragma unmanaged`. Si une exception structurée est levée dans le code managé qui doit être mappé, le code qui génère et gère l'exception doit être marqué avec le `pragma`. Le code suivant illustre une utilisation possible. Pour plus d’informations, consultez [Directives pragma et mot clé __Pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md).  
  
```  
// crt_set_se_translator_clr.cpp  
// compile with: /clr  
#include <windows.h>  
#include <eh.h>  
#include <assert.h>  
#include <stdio.h>  
  
int thrower_func(int i) {  
   int j = i/0;  
  return 0;  
}  
  
class CMyException{  
};  
  
#pragma unmanaged  
void my_trans_func(unsigned int u, PEXCEPTION_POINTERS pExp )  
{  
printf("Translating the structured exception to a C++"  
             " exception.\n");  
throw CMyException();  
}  
  
void DoTest()  
{  
    try  
    {  
      thrower_func(10);  
    }   
  
    catch(CMyException e)  
    {  
printf("Caught CMyException.\n");  
    }  
    catch(...)  
    {  
      printf("Caught unexpected SEH exception.\n");  
    }  
}  
#pragma managed  
  
int main(int argc, char** argv) {  
    _set_se_translator(my_trans_func);  
    DoTest();  
    return 0;  
}  
```  
  
```Output  
Translating the structured exception to a C++ exception.  
Caught CMyException.  
```  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de gestion des exceptions](../../c-runtime-library/exception-handling-routines.md)   
 [set_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [set_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [unexpected](../../c-runtime-library/reference/unexpected-crt.md)
