---
title: "appdomain | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "appdomain_cpp"
  - "appdomain"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec (mot clé) (C++), appdomain"
  - "appdomain __declspec (mot clé)"
ms.assetid: 29d843cb-cb6b-4d1b-a48d-d928a877234d
caps.latest.revision: 23
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# appdomain
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifie que chaque domaine d'application de votre application managée doit avoir sa propre copie d'une variable globale ou d'une variable membre static particulière.  Pour plus d'informations, consultez [Domaines d'application et Visual C\+\+](../dotnet/application-domains-and-visual-cpp.md).  
  
 Chaque domaine d'application a sa propre copie d'une variable par domaine d'application.  Un constructeur d'une variable de domaine d'application est exécuté lorsqu'un assembly est chargé dans un domaine d'application, et le destructeur est exécuté lorsque le domaine d'application est déchargé.  
  
 Si vous voulez que tous les domaines d'application au sein d'un processus dans le Common Langage Runtime partagent une variable globale, utilisez le modificateur `__declspec(process)`.  `__declspec(process)` est appliqué par défaut sous [\/clr](../build/reference/clr-common-language-runtime-compilation.md) et `__declspec(appdomain)` est appliqué par défaut sous **\/clr:pure**.  `__declspec(appdomain)` est appliqué sous **\/clr:safe**.  
  
 `__declspec(appdomain)` est valide uniquement lorsque l'une des options **\/clr** du compilateur est utilisée.  Seules une variable globale, une variable membre static ou une variable locale static peuvent être marquées avec `__declspec(appdomain)`.  Il est incorrect d'appliquer `__declspec(appdomain)` aux membres static des types managés, car ils ont toujours ce comportement.  
  
 L'utilisation de `__declspec(appdomain)` est semblable à celle du [stockage local des threads \(TLS\)](../parallel/thread-local-storage-tls.md).  Les threads ont leur propre stockage, tout comme les domaines d'application.  L'utilisation de `__declspec(appdomain)` assure que la variable globale possède son propre stockage dans chaque domaine d'application créé pour cette application.  
  
 Il existe des limites concernant l'association de variables par processus et par domaine d'application ; consultez [processus](../cpp/process.md) pour plus d'informations.  
  
 Par exemple, au lancement du programme, toutes les variables par processus sont initialisées, puis toutes les variables par domaine d'application.  Par conséquent, lorsqu'une variable par processus est en cours d'initialisation, elle ne peut pas dépendre de la valeur d'une quelconque variable par domaine d'application.  Il n'est pas recommandé de combiner l'utilisation \(assignation\) de variables par processus et par domaine d'application.  
  
 Pour obtenir des informations sur la façon d'appeler une fonction dans un domaine d'application spécifique, consultez [call\_in\_appdomain, fonction](../dotnet/call-in-appdomain-function.md).  
  
## Exemple  
  
```  
// declspec_appdomain.cpp  
// compile with: /clr  
#include <stdio.h>  
using namespace System;  
  
class CGlobal {  
public:  
   CGlobal(bool bProcess) {  
      Counter = 10;  
      m_bProcess = bProcess;  
      Console::WriteLine("__declspec({0}) CGlobal::CGlobal constructor", m_bProcess ? (String^)"process" : (String^)"appdomain");  
   }  
  
   ~CGlobal() {  
      Console::WriteLine("__declspec({0}) CGlobal::~CGlobal destructor", m_bProcess ? (String^)"process" : (String^)"appdomain");  
   }  
  
   int Counter;  
  
private:  
   bool m_bProcess;  
};  
  
__declspec(process) CGlobal process_global = CGlobal(true);  
__declspec(appdomain) CGlobal appdomain_global = CGlobal(false);  
  
value class Functions {  
public:  
   static void change() {  
      ++appdomain_global.Counter;  
   }  
  
   static void display() {  
      Console::WriteLine("process_global value in appdomain '{0}': {1}",   
         AppDomain::CurrentDomain->FriendlyName,  
         process_global.Counter);  
  
      Console::WriteLine("appdomain_global value in appdomain '{0}': {1}",   
         AppDomain::CurrentDomain->FriendlyName,  
         appdomain_global.Counter);  
   }  
};  
  
int main() {  
   AppDomain^ defaultDomain = AppDomain::CurrentDomain;  
   AppDomain^ domain = AppDomain::CreateDomain("Domain 1");  
   AppDomain^ domain2 = AppDomain::CreateDomain("Domain 2");  
   CrossAppDomainDelegate^ changeDelegate = gcnew CrossAppDomainDelegate(&Functions::change);  
   CrossAppDomainDelegate^ displayDelegate = gcnew CrossAppDomainDelegate(&Functions::display);  
  
   // Print the initial values of appdomain_global in all appdomains.  
   Console::WriteLine("Initial value");  
   defaultDomain->DoCallBack(displayDelegate);  
   domain->DoCallBack(displayDelegate);  
   domain2->DoCallBack(displayDelegate);  
  
   // Changing the value of appdomain_global in the domain and domain2  
   // appdomain_global value in "default" appdomain remain unchanged  
   process_global.Counter = 20;  
   domain->DoCallBack(changeDelegate);  
   domain2->DoCallBack(changeDelegate);  
   domain2->DoCallBack(changeDelegate);  
  
   // Print values again  
   Console::WriteLine("Changed value");  
   defaultDomain->DoCallBack(displayDelegate);  
   domain->DoCallBack(displayDelegate);  
   domain2->DoCallBack(displayDelegate);  
  
   AppDomain::Unload(domain);  
   AppDomain::Unload(domain2);  
}  
```  
  
  **\_\_declspec\(process\) CGlobal::CGlobal constructor**  
**\_\_declspec\(appdomain\) CGlobal::CGlobal constructor**  
**Valeur initiale**  
**process\_global value in appdomain 'declspec\_appdomain.exe': 10**  
**appdomain\_global value in appdomain 'declspec\_appdomain.exe': 10**  
**\_\_declspec\(appdomain\) CGlobal::CGlobal constructor**  
**process\_global value in appdomain 'Domain 1': 10**  
**appdomain\_global value in appdomain 'Domain 1': 10**  
**\_\_declspec\(appdomain\) CGlobal::CGlobal constructor**  
**process\_global value in appdomain 'Domain 2': 10**  
**appdomain\_global value in appdomain 'Domain 2': 10**  
**Valeur modifiée**  
**process\_global value in appdomain 'declspec\_appdomain.exe': 20**  
**appdomain\_global value in appdomain 'declspec\_appdomain.exe': 10**  
**process\_global value in appdomain 'Domain 1': 20**  
**appdomain\_global value in appdomain 'Domain 1': 11**  
**process\_global value in appdomain 'Domain 2': 20**  
**appdomain\_global value in appdomain 'Domain 2': 12**  
**\_\_declspec\(appdomain\) CGlobal::~CGlobal destructor**  
**\_\_declspec\(appdomain\) CGlobal::~CGlobal destructor**  
**\_\_declspec\(appdomain\) CGlobal::~CGlobal destructor**  
**\_\_declspec\(process\) CGlobal::~CGlobal destructor**   
## Voir aussi  
 [\_\_declspec](../cpp/declspec.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)