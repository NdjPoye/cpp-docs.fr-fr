---
title: "Diff&#233;rences du comportement de gestion des exceptions dans /CLR | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EXCEPTION_CONTINUE_EXECUTION (macro)"
  - "set_se_translator (fonction)"
ms.assetid: 2e7e8daf-d019-44b0-a51c-62d7aaa89104
caps.latest.revision: 20
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Diff&#233;rences du comportement de gestion des exceptions dans /CLR
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[Concepts de base utilisant des exceptions managées](../dotnet/basic-concepts-in-using-managed-exceptions.md) traite de la gestion des exceptions dans les applications managées.  Dans cette rubrique, les différences de comportement standard de la gestion des exceptions et restrictions sont présentées en détail.  Pour plus d'informations sur les fonctions de traduction d'exceptions, consultez [The \_set\_se\_translator Function](../c-runtime-library/reference/set-se-translator.md).  
  
##  <a name="vcconjumpingoutofafinallyblock"></a> Ignorer enfin d'un bloc  
 En code natif de C\/C\+\+, il permet d'ignorer un bloc de**finally** de à l'aide de la gestion des exceptions structurées \(SEH\) bien qu'il déclenche un avertissement.  Sous [\/clr](../build/reference/clr-common-language-runtime-compilation.md), ignorer d'un bloc de **finally** génère une erreur :  
  
```  
// clr_exception_handling_4.cpp  
// compile with: /clr  
int main() {  
   try {}  
   finally {  
      return 0;   // also fails with goto, break, continue  
    }  
}   // C3276  
```  
  
##  <a name="vcconraisingexceptionswithinanexceptionfilter"></a> Déclenchement d'exceptions dans un filtre d'exceptions  
 Lorsqu'une exception est levée pendant le traitement d'un [filtre d'exceptions](../cpp/writing-an-exception-filter.md) dans le code managé, l'exception est interceptée et traitée comme si retourne la valeur 0 de filtre.  
  
 Ce comportement diffère du comportement en code natif où une exception imbriquée est générée, le champ d'**ExceptionRecord** dans la structure d'**EXCEPTION\_RECORD** \(retourné par [GetExceptionInformation](http://msdn.microsoft.com/library/windows/desktop/ms679357)\) a la valeur, les ensembles de champs d'**ExceptionFlags** le bit 0x10.  La différence est illustrée dans l'exemple suivant.  
  
```  
// clr_exception_handling_5.cpp  
#include <windows.h>  
#include <stdio.h>  
#include <assert.h>  
  
#ifndef false  
#define false 0  
#endif  
  
int *p;  
  
int filter(PEXCEPTION_POINTERS ExceptionPointers) {  
   PEXCEPTION_RECORD ExceptionRecord =   
                     ExceptionPointers->ExceptionRecord;  
  
   if ((ExceptionRecord->ExceptionFlags & 0x10) == 0) {  
      // not a nested exception, throw one  
      *p = 0; // throw another AV  
   }  
   else {  
      printf("Caught a nested exception\n");  
      return 1;  
    }  
  
   assert(false);  
  
   return 0;  
}  
  
void f(void) {  
   __try {  
      *p = 0;   // throw an AV  
   }  
   __except(filter(GetExceptionInformation())) {  
      printf_s("We should execute this handler if "  
                 "compiled to native\n");  
    }  
}  
  
int main() {  
   __try {  
      f();  
   }  
   __except(1) {  
      printf_s("The handler in main caught the "  
               "exception\n");  
    }  
}  
```  
  
### Sortie  
  
```  
Caught a nested exception  
We should execute this handler if compiled to native  
```  
  
##  <a name="vccondisassociatedrethrows"></a> Rethrows dissocié  
 **\/clr** ne prend pas en charge rethrowing une exception en dehors d'un gestionnaire CATCH \(appelé rethrow dissocié\).  Les exceptions de ce type sont traitées comme rethrow standard C\+\+.  Si un rethrow est dissocié lorsqu'il y a une exception managée active, l'exception est encapsulée comme exception puis rethrown du actuel \+\+ c.  Les exceptions de ce type peuvent être interceptées comme exception de type [System::SEHException](https://msdn.microsoft.com/en-us/library/system.runtime.interopservices.sehexception.aspx).  
  
 L'exemple suivant illustre un rethrown managé d'exception comme exception actuelle \+\+ c :  
  
```  
// clr_exception_handling_6.cpp  
// compile with: /clr  
using namespace System;  
#include <assert.h>  
#include <stdio.h>  
  
void rethrow( void ) {  
   // This rethrow is a dissasociated rethrow.  
   // The exception would be masked as SEHException.  
   throw;  
}  
  
int main() {  
   try {  
      try {  
         throw gcnew ApplicationException;  
      }  
      catch ( ApplicationException^ ) {  
         rethrow();  
         // If the call to rethrow() is replaced with  
         // a throw statement within the catch handler,  
         // the rethrow would be a managed rethrow and  
         // the exception type would remain   
         // System::ApplicationException  
      }  
   }  
  
    catch ( ApplicationException^ ) {  
      assert( false );  
  
      // This will not be executed since the exception  
      // will be masked as SEHException.  
    }  
   catch ( Runtime::InteropServices::SEHException^ ) {  
      printf_s("caught an SEH Exception\n" );  
    }  
}  
```  
  
### Sortie  
  
```  
caught an SEH Exception  
```  
  
##  <a name="vcconexceptionfiltersandexception_continue_execution"></a> Filtres d'exceptions et EXCEPTION\_CONTINUE\_EXECUTION  
 Si un filtre retourne `EXCEPTION_CONTINUE_EXECUTION` dans une application managée, il est considéré comme si le filtre retournait `EXCEPTION_CONTINUE_SEARCH`.  Pour plus d'informations sur ces constantes, consultez [TRY\-excepté l'instruction](../cpp/try-except-statement.md).  
  
 L'exemple suivant illustre ces différences clés.  
  
```  
// clr_exception_handling_7.cpp  
#include <windows.h>  
#include <stdio.h>  
#include <assert.h>  
  
int main() {  
   int Counter = 0;  
   __try {  
      __try  {  
         Counter -= 1;  
         RaiseException (0xe0000000|'seh',  
                         0, 0, 0);  
         Counter -= 2;  
      }  
      __except (Counter) {  
         // Counter is negative,  
         // indicating "CONTINUE EXECUTE"  
         Counter -= 1;  
      }  
    }  
    __except(1) {  
      Counter -= 100;  
   }  
  
   printf_s("Counter=%d\n", Counter);  
}  
```  
  
### Sortie  
  
```  
Counter=-3  
```  
  
##  <a name="vcconthe_set_se_translatorfunction"></a> The\_set\_se\_translator \(fonction\)  
 La fonction de transcodage, définie par un appel à `_set_se_translator`, catch d'attribut affecte uniquement en code non managé.  L'exemple suivant illustre la procédure à suivre pour réaliser cette limitation :  
  
```  
// clr_exception_handling_8.cpp  
// compile with: /clr /EHa  
#include <iostream>  
#include <windows.h>  
#include <eh.h>  
#pragma warning (disable: 4101)  
using namespace std;  
using namespace System;  
  
#define MYEXCEPTION_CODE 0xe0000101  
  
class CMyException {  
public:  
   unsigned int m_ErrorCode;  
   EXCEPTION_POINTERS * m_pExp;  
  
   CMyException() : m_ErrorCode( 0 ), m_pExp( NULL ) {}  
  
   CMyException( unsigned int i, EXCEPTION_POINTERS * pExp )  
         : m_ErrorCode( i ), m_pExp( pExp ) {}  
  
   CMyException( CMyException& c ) : m_ErrorCode( c.m_ErrorCode ),  
                                      m_pExp( c.m_pExp ) {}  
  
   friend ostream& operator <<   
                 ( ostream& out, const CMyException& inst ) {  
      return out <<  "CMyException[\n" <<    
             "Error Code: " << inst.m_ErrorCode <<  "]";  
    }  
};  
  
#pragma unmanaged   
void my_trans_func( unsigned int u, PEXCEPTION_POINTERS pExp ) {  
   cout <<  "In my_trans_func.\n";  
   throw CMyException( u, pExp );  
}  
  
#pragma managed   
void managed_func() {  
   try  {  
      RaiseException( MYEXCEPTION_CODE, 0, 0, 0 );  
   }  
   catch ( CMyException x ) {}  
   catch ( ... ) {  
      printf_s("This is invoked since "  
               "_set_se_translator is not "  
               "supported when /clr is used\n" );  
    }  
}  
  
#pragma unmanaged   
void unmanaged_func() {  
   try  {  
      RaiseException( MYEXCEPTION_CODE,   
                      0, 0, 0 );  
   }  
   catch ( CMyException x ) {  
      printf("Caught an SEH exception with "  
             "exception code: %x\n", x.m_ErrorCode );  
    }  
    catch ( ... ) {}  
}  
  
// #pragma managed   
int main( int argc, char ** argv ) {  
   _set_se_translator( my_trans_func );  
  
   // It does not matter whether the translator function  
   // is registered in managed or unmanaged code  
   managed_func();  
   unmanaged_func();  
}  
```  
  
### Sortie  
  
```  
This is invoked since _set_se_translator is not supported when /clr is used  
In my_trans_func.  
Caught an SEH exception with exception code: e0000101  
```  
  
## Voir aussi  
 [Exception Handling](../windows/exception-handling-cpp-component-extensions.md)   
 [safe\_cast](../windows/safe-cast-cpp-component-extensions.md)   
 [Gestion des exceptions](../cpp/exception-handling-in-visual-cpp.md)