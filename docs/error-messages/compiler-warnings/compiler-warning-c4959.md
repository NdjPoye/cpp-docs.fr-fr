---
title: "Avertissement du compilateur C4959 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4959"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4959"
ms.assetid: 3a128f3e-4d8a-4565-ba1a-5d32fdeb5982
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur C4959
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Impossible de définir le struct 'type' non managé en \/clr:safe, car l’accès à ses membres génère du code non vérifiable  
  
 L’accès à un membre d’un type non managé entraîne la création d’une image non vérifiable \(peverify.exe\).  
  
 Pour plus d'informations, consultez [Code pur et vérifiable](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
 Cet avertissement s’affiche comme une erreur et peut être désactivé avec le pragma [warning](../../preprocessor/warning.md) ou l’option du compilateur [\/wd](../../build/reference/compiler-option-warning-level.md).  
  
 L’exemple suivant génère l’erreur C4959.  
  
```  
// C4959.cpp // compile with: /clr:safe // Uncomment the following line to resolve. // #pragma warning( disable : 4959 ) struct X { int data; }; int main() { X x; x.data = 10;   // C4959 }  
```