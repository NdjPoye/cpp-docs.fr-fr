---
title: "Avertissement du compilateur C4950 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4950"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4950"
ms.assetid: 50226a5c-c664-4d09-ac59-e9e874ca244f
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Avertissement du compilateur C4950
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type\_ou\_membre' : marqué comme obsolète  
  
 Un membre ou un type a été marqué comme obsolète avec [ObsoleteAttribute](frlrfSystemObsoleteAttributeClassTopic).  
  
 L’avertissement C4950 est toujours présenté comme une erreur.  Vous pouvez désactiver cet avertissement avec `#pragma warning` ou **\/wd** Pour plus d’informations, consultez [warning](../../preprocessor/warning.md) ou [\/w, \/Wn, \/WX, \/Wall, \/wln, \/wdn, \/wen, \/won \(Niveau d'avertissement\)](../../build/reference/compiler-option-warning-level.md).  
  
 L’exemple suivant génère l’erreur C4950 :  
  
```  
// C4950.cpp // compile with: /clr using namespace System; // Any reference to Func3 should generate an error with message [System::ObsoleteAttribute("Will be removed in next version", true)] Int32 Func3(Int32 a, Int32 b) { return (a + b); } int main() { Int32 MyInt3 = ::Func3(2, 2);   // C4950 }  
```