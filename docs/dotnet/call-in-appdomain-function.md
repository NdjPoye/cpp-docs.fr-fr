---
title: "call_in_appdomain, fonction | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "call_in_appdomain"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "call_in_appdomain (fonction)"
ms.assetid: 9a1a5026-b76b-4cae-a3d4-29badeb9db9c
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# call_in_appdomain, fonction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Exécute une fonction dans un domaine d'application spécifié.  
  
## Syntaxe  
  
```  
template <typename ArgType1, ...typename ArgTypeN>  
void call_in_appdomain(  
   DWORD appdomainId,  
   void (*voidFunc)(ArgType1, ...ArgTypeN) [ ,  
   ArgType1 arg1,  
   ...  
   ArgTypeN argN ]  
);  
template <typename RetType, typename ArgType1, ...typename ArgTypeN>  
RetType call_in_appdomain(  
   DWORD appdomainId,  
   RetType (*nonvoidFunc)(ArgType1, ...ArgTypeN) [ ,  
   ArgType1 arg1,  
   ...  
   ArgTypeN argN ]  
);  
```  
  
#### Paramètres  
 `appdomainId`  
 AppDomain dans lequel appeler la fonction.  
  
 `voidFunc`  
 Pointeur vers une fonction `void` qui prend les N paramètres \(0 \<\= N \<\= 15\).  
  
 `nonvoidFunc`  
 Pointeur vers une non\-`void` fonction qui prend les N paramètres \(0 \<\= N \<\= 15\).  
  
 `arg1...argN`  
 Zéro à 15 paramètres à transmettre à `voidFunc` ou à `nonvoidFunc` dans l'autre appdomain.  
  
## Valeur de retour  
 Le résultat de l'exécution `voidFunc` ou `nonvoidFunc` dans le domaine spécifié de l'application.  
  
## Notes  
 Les arguments de la fonction passée à `call_in_appdomain` ne doivent pas être des types CLR.  
  
## Exemple  
  
```  
// msl_call_in_appdomain.cpp  
// compile with: /clr  
  
// Defines two functions: one takes a parameter and returns nothing,  
// the other takes no parameters and returns an int.  Calls both  
// functions in the default appdomain and in a newly-created  
// application domain using call_in_appdomain.  
  
#include <msclr\appdomain.h>  
  
using namespace System;  
using namespace msclr;  
  
void PrintCurrentDomainName( char* format )  
{  
   String^ s = gcnew String(format);  
   Console::WriteLine( s, AppDomain::CurrentDomain->FriendlyName );  
}  
  
int GetDomainId()  
{  
   return AppDomain::CurrentDomain->Id;  
}  
  
int main()  
{  
   AppDomain^ appDomain1 = AppDomain::CreateDomain( "First Domain" );  
  
   call_in_appdomain( AppDomain::CurrentDomain->Id,  
                   &PrintCurrentDomainName,  
                   (char*)"default appdomain: {0}" );  
   call_in_appdomain( appDomain1->Id,  
                   &PrintCurrentDomainName,  
                   (char*)"in appDomain1: {0}" );  
  
   int id;  
   id = call_in_appdomain( AppDomain::CurrentDomain->Id, &GetDomainId );  
   Console::WriteLine( "default appdomain id = {0}", id );  
   id = call_in_appdomain( appDomain1->Id, &GetDomainId );  
   Console::WriteLine( "appDomain1 id = {0}", id );  
}  
```  
  
## Sortie  
  
```  
default appdomain: msl_call_in_appdomain.exe  
in appDomain1: First Domain  
default appdomain id = 1  
appDomain1 id = 2  
```  
  
## Configuration requise  
 \<**Fichier d'en\-tête** msclr\\appdomain.h\>  
  
 **Nom de l'espace** msclr