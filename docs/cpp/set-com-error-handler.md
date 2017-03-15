---
title: "_set_com_error_handler | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_set_com_error_handler (fonction)"
ms.assetid: 49fe4fca-5e37-4d83-abaf-15be5ce37f94
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# _set_com_error_handler
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Remplace la fonction par défaut utilisée pour la gestion des erreurs COM.  
  
## Syntaxe  
  
```  
void __stdcall _set_com_error_handler(  
   void (__stdcall *pHandler)(  
      HRESULT hr,   
      IErrorInfo* perrinfo  
   )  
);  
```  
  
#### Paramètres  
 `pHandler`  
 Pointeur vers la fonction de remplacement.  
  
 `hr`  
 Informations `HRESULT`.  
  
 `perrinfo`  
 Objet `IErrorInfo`.  
  
## Notes  
 Par défaut, [\_com\_raise\_error](../cpp/com-raise-error.md) gère toutes les erreurs COM.  Vous pouvez modifier ce comportement en utilisant `_set_com_error_handler` pour appeler votre propre fonction de gestion des erreurs.  
  
 La fonction de remplacement doit avoir une signature qui est équivalente à celle de `_com_raise_error`.  
  
## Exemple  
  
```  
// _set_com_error_handler.cpp  
// compile with /EHsc  
#include <stdio.h>  
#include <comdef.h>  
#include <comutil.h>  
  
// Importing ado dll to attempt to establish an ado connection.  
// Not related to _set_com_error_handler   
#import "C:\Program Files\Common Files\System\ado\msado15.dll" no_namespace rename("EOF", "adoEOF")  
  
void __stdcall _My_com_raise_error(HRESULT hr, IErrorInfo* perrinfo)  
{  
   throw "Unable to establish the connection!";  
}  
  
int main()  
{  
   _set_com_error_handler(_My_com_raise_error);  
   _bstr_t bstrEmpty(L"");  
   _ConnectionPtr Connection = NULL;  
   try  
   {  
      Connection.CreateInstance(__uuidof(Connection));  
      Connection->Open(bstrEmpty, bstrEmpty, bstrEmpty, 0);   
   }  
   catch(char* errorMessage)  
   {  
      printf("Exception raised: %s\n", errorMessage);  
   }  
  
   return 0;  
}  
```  
  
  **Exception levée : impossible d'établir la connexion \!**   
## Configuration requise  
 **En\-tête :** comdef.h  
  
 **Lib :**si l'option de compilateur « wchar\_t est le type natif » est activée, utilisez comsuppw.lib ou le comsuppwd.lib.  Si l'option « wchar\_t est le type natif » est désactivée, utilisez comsupp.lib.  Pour plus d'informations, consultez [\/Zc:wchar\_t \(wchar\_t est un type natif\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).  
  
## Voir aussi  
 [Fonctions globales COM du compilateur](../cpp/compiler-com-global-functions.md)