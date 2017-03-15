---
title: "Avertissement du compilateur C4957 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4957"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4957"
ms.assetid: a18c52d4-23e2-44f1-b4b5-f7fa5a7f3987
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# Avertissement du compilateur C4957
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'cast' : le cast explicite de 'cast\_from' en 'cast\_to' n’est pas vérifiable  
  
 Un cast aura pour résultat une image non vérifiable.  
  
 Certains casts sont « safe » \(par exemple, un `static_cast` qui déclenche des conversions définies par l’utilisateur et un `const_cast`\). Un [safe\_cast](../../windows/safe-cast-cpp-component-extensions.md) garantit la génération d’un code vérifiable.  
  
 Pour plus d’informations, consultez [Code pur et vérifiable](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
 Cet avertissement s’affiche comme une erreur et peut être désactivé avec le pragma [warning](../../preprocessor/warning.md) ou l’option du compilateur [\/wd](../../build/reference/compiler-option-warning-level.md).  
  
 L’exemple suivant génère l’erreur C4957 :  
  
```  
// C4957.cpp // compile with: /clr:safe // #pragma warning( disable : 4957 ) using namespace System; int main() { Object ^ o = "Hello, World!"; String ^ s = static_cast<String^>(o);   // C4957 String ^ s2 = safe_cast<String^>(o);   // OK }  
```