---
title: "_set_se_translator | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_se_translator"
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
  - "_set_se_translator"
  - "set_se_translator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_set_se_translator (fonction)"
  - "gestion des exceptions, modifier"
  - "set_se_translator (fonction)"
ms.assetid: 280842bc-d72a-468b-a565-2d3db893ae0f
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _set_se_translator
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gère les exceptions Win32 \(exceptions structurées C\) comme des exceptions tapées en C\+\+.  
  
## Syntaxe  
  
```  
_se_translator_function _set_se_translator(  
   _se_translator_function seTransFunction  
);  
```  
  
#### Paramètres  
 `seTransFunction`  
 Le pointeur vers une la fonction de transcodage d'exception de structure C que vous écrivez.  
  
## Valeur de retour  
 Retourne un pointeur vers la fonction de traduction précédente d'arrêt indiquée par `_set_se_translator` afin que la fonction précédente puisse être restaurée plus tard.  Si aucune fonction n'est définie, la valeur de retour peut être utilisée pour restaurer le comportement par défaut ; cette valeur peut être NULL.  
  
## Notes  
 La fonction `_set_se_translator` permet de gérer les exceptions Win32 \(exceptions de structure C\) en tant que des exceptions C\+\+.  Pour permettre à exception C d'être gérée par un gestionnaire C\+\+ `catch`, définissez d'abord la classe wrapper C d'exception qui peut être utilisé, ou dérivé, pour attribuer un type spécifique de la classe à l'exception en C.  Pour utiliser cette classe, installez une fonction de traduction d'exception C personnalisée appelée par le mécanisme de gestion des exceptions interne chaque fois qu'une exception C est relevée.  Dans votre fonction de transcodage, vous pouvez lever toute exception non typée qui peut être interceptée par un gestionnaire de `catch` C\+\+.  
  
 Vous devez utiliser [\/EHa](../../build/reference/eh-exception-handling-model.md) en utilisant `_set_se_translator`.  
  
 Pour spécifier une fonction de traduction personnalisée, appelez la fonction  `_set_se_translator`  avec le nom de votre fonction de traduction comme unique argument.  La fonction de traduction que vous écrivez est appelée une fois pour chaque appel de fonction sur la pile qui a des blocs `try` .  Il n'existe aucune fonction de transcodage par défaut.  
  
 Votre fonction de transcodage ne doit pas faire plus que le renvoi d'une exeption typée C\+\+.  Si elle fait quoi que ce soit de plus \(comme l'écriture d'un fichier journal, par exemple\) votre programme peut ne pas se comporter comme prévu, car le nombre de fois où la fonction de transcodage est appelée est indépendant de la plateforme.  
  
 Dans un environnement multithread, les fonctions de traduction sont contenues séparément pour chaque thread.  Chacun des nouveaux threads a beson d'installer sa propre fonctionde traduction.  Par conséquent, chaque thread est responsable de sa propre gestion de traduction.  `_set_se_translator` est spécifique à un thread ; un autre DLL peut installer une fonction de traduction différente.  
  
 La fonction `seTransFunction` que vous entrez doit être une fonction natve \- fonction compilée \(non compilée avec \/clr\).  Elle doit prendre un entier non signé et un pointeur vers une structure Win32 `_EXCEPTION_POINTERS` comme arguments.  Les arguments sont les valeurs retournées par des appels aux fonctions API Win32 `GetExceptionCode` et `GetExceptionInformation`, respectivement.  
  
```  
typedef void (*_se_translator_function)(unsigned int, struct _EXCEPTION_POINTERS* );  
```  
  
 Pour `_set_se_translator`, il y a des conséquences lier dynamiquement au CRT ; un autre DLL dans le processus peut appeler `_set_se_translator` et remplacer le gestionnaire par le sien.  
  
 Lorsque vous utilisez `_set_se_translator` de code managé \(codes compilés avec \/clr\) ou du natif mixte et du code managé, sachez que le traducteur affecte les exceptions générées dans code natif uniquement.  Aucune exception managée générée en code managé \(par exemple en déclenchant `System::Exception`\) n'est acheminée par le biais de la fonction de transcodage.  Les exceptions générées en code managé à l'aide de la fonction Win32`RaiseException` ou provoquées par une exception système comme une division par zéro sont retournés vers le traducteur.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_set_se_translator`|\<EH.H\>|  
  
 Les fonctionnalités fournies par `_set_se_translator` ne sont pas disponibles dans le code compilé avec l'option du compilateur [\/clr:pure](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
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
  
  **In trans\_func.**  
**In finally**  
**Caught a \_\_try exception with SE\_Exception.**   
## Exemple  
 Bien que les fonctionnalités fournies par `_set_se_translator` ne sont pas disponibles en code managé, il est possible d'utiliser ce mapping en code natif, même si le code natif est dans une compilation sous le switch `/clr`, tant que le code natif est affiché grâce à `#pragma unmanaged`.  Si une exception structurée est relevée en code managé qui doit être mappé, le code qui produit et gère l'exception doit être identifié par `pragma`.  Le code suivant illustre une utilisation possible.  Pour plus d'informations, consultez [Directives pragma et mot clé \_Pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md).  
  
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
  
  **Traduction de l'exception structurées vers une exception en C\+\+.**  
**CMyException intercepté.**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Routines de la gestion d'exceptions](../../c-runtime-library/exception-handling-routines.md)   
 [set\_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [set\_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [inattendu](../../c-runtime-library/reference/unexpected-crt.md)