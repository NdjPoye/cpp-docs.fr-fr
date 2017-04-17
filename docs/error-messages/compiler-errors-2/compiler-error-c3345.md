---
title: "Erreur du compilateur C3345 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3345"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3345"
ms.assetid: 1dda4c79-73bb-441b-b939-746154c3afba
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# Erreur du compilateur C3345
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : identificateur non valide pour le nom de module  
  
 L’*identificateur* d’un module contient un ou plusieurs caractères inacceptables. Un identificateur est valide si le premier caractère est un caractère alphabétique, un caractère de soulignement ou un caractère ANSI élevé \(0x80\-FF\), et que tout caractère suivant est un caractère alphanumérique, un caractère de soulignement ou un caractère ANSI élevé.  
  
### Pour corriger cette erreur  
  
1.  Vérifiez que l’*identificateur* ne contient pas d’espaces ni d’autres caractères inacceptables.  
  
## Exemple  
 L’exemple de code suivant provoque le message d’erreur C3345, car le paramètre `name` de l’attribut `module` contient un espace.  
  
```  
// cpp_attr_name_module.cpp // compile with: /LD /link /OPT:NOREF #include <atlbase.h> #include <atlcom.h> #include <atlwin.h> #include <atltypes.h> #include <atlctl.h> #include <atlhost.h> #include <atlplus.h> // C3345 expected [module(dll, name="My Library", version="1.2", helpfile="MyHelpFile")] // Try the following line instead //[module(dll, name="MyLibrary", version="1.2", helpfile="MyHelpFile")] // Module attribute now applies to this class class CMyClass { public: BOOL WINAPI DllMain(DWORD dwReason, LPVOID lpReserved) { // add your own code here return __super::DllMain(dwReason, lpReserved); } };  
```  
  
## Voir aussi  
 [\_\_iscsym](../../c-runtime-library/reference/iscsym-functions.md)   
 [Classifications des caractères](../../c-runtime-library/character-classification.md)   
 [module](../../windows/module-cpp.md)