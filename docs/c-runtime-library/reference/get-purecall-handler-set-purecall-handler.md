---
title: "_get_purecall_handler, _set_purecall_handler | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_purecall_handler"
  - "_set_purecall_handler_m"
  - "_get_purecall_handler"
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
  - "_set_purecall_handler"
  - "_set_purecall_handler_m"
  - "set_purecall_handler_m"
  - "set_purecall_handler"
  - "stdlib/_set_purecall_handler"
  - "stdlib/_get_purecall_handler"
  - "_get_purecall_handler"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_set_purecall_handler (fonction)"
  - "set_purecall_handler (fonction)"
  - "purecall_handler"
  - "set_purecall_handler_m (fonction)"
  - "_purecall_handler"
  - "_set_purecall_handler_m (fonction)"
  - "_get_purecall_handler (fonction)"
ms.assetid: 2759b878-8afa-4129-86e7-72afc2153d9c
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _get_purecall_handler, _set_purecall_handler
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient ou définit le Gestionnaire d’erreurs pour un appel de fonction virtuelle pure.  
  
## Syntaxe  
  
```  
typedef void (__cdecl* _purecall_handler)(void);  
  
_purecall_handler __cdecl _get_purecall_handler(void);  
  
_purecall_handler __cdecl _set_purecall_handler(   
   _purecall_handler function  
);  
```  
  
#### Paramètres  
 `function`  
 Fonction à appeler quand une fonction virtuelle pure est appelée. Une fonction `_purecall_handler` doit avoir un type de retour void.  
  
## Valeur de retour  
 `_purecall_handler` précédent. Retourne `nullptr` s'il n'existait pas de gestionnaire précédemment.  
  
## Notes  
 Le `_get_purecall_handler` et `_set_purecall_handler` fonctions sont spécifiques à Microsoft et s’appliquent uniquement au code C\+\+.  
  
 Un appel à une fonction virtuelle pure est une erreur, car il n’a aucune implémentation. Par défaut, le compilateur génère du code pour appeler une fonction de gestionnaire d’erreurs lorsqu’une fonction virtuelle pure est appelée, ce qui met fin au programme. Vous pouvez installer votre propre fonction de gestionnaire d’erreurs pour les appels de fonction virtuelle pure, pour intercepter les fins de débogage ou de création de rapports. Pour utiliser votre propre gestionnaire d’erreurs, créez une fonction qui possède le `_purecall_handler` signature, puis utiliser `_set_purecall_handler` afin de faciliter le gestionnaire en cours.  
  
 Étant donné qu’un seul `_purecall_handler` pour chaque processus, lorsque vous appelez `_set_purecall_handler` son impact immédiatement sur tous les threads. Le dernier appelant au niveau d'un thread est celui qui définit le gestionnaire.  
  
 Pour restaurer le comportement par défaut, appelez `_set_purecall_handler` en utilisant un `nullptr` argument.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_get_purecall_handler`, `_set_purecall_handler`|\< cstdlib \> ou \< stdlib.h \>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// _set_purecall_handler.cpp  
// compile with: /W1  
#include <tchar.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
class CDerived;  
class CBase  
{  
public:  
   CBase(CDerived *derived): m_pDerived(derived) {};  
   ~CBase();  
   virtual void function(void) = 0;  
  
   CDerived * m_pDerived;  
};  
  
class CDerived : public CBase  
{  
public:  
   CDerived() : CBase(this) {};   // C4355  
   virtual void function(void) {};  
};  
  
CBase::~CBase()  
{  
   m_pDerived -> function();  
}  
  
void myPurecallHandler(void)  
{  
   printf("In _purecall_handler.");  
   exit(0);  
}  
  
int _tmain(int argc, _TCHAR* argv[])  
{  
   _set_purecall_handler(myPurecallHandler);  
   CDerived myDerived;  
}  
```  
  
```Output  
In _purecall_handler.  
```  
  
## Voir aussi  
 [Gestion des erreurs](../../c-runtime-library/error-handling-crt.md)   
 [\_purecall](../../c-runtime-library/reference/purecall.md)