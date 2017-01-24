---
title: "Avertissement du compilateur C4439 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4439"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4439"
ms.assetid: 9449958f-f407-4824-829b-9e092f2af97d
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur C4439
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : une définition de fonction avec un type managé dans la signature doit avoir une convention d'appel \_\_clrcall  
  
 Le compilateur a remplacé implicitement une convention d'appel par [\_\_clrcall](../../cpp/clrcall.md).  Pour remédier à cet avertissement, supprimez la convention d'appel `__cdecl` ou `__stdcall`.  
  
 C4439 est toujours émis en tant qu'erreur.  Vous pouvez désactiver cet avertissement avec `#pragma warning` ou **\/wd** ; consultez [warning](../../preprocessor/warning.md) ou [\/w, \/Wn, \/WX, \/Wall, \/wln, \/wdn, \/wen, \/won \(Niveau d'avertissement\)](../../build/reference/compiler-option-warning-level.md) pour plus d'informations.  
  
## Exemple  
 L'exemple suivant génère l'erreur C4439 :  
  
```  
// C4439.cpp  
// compile with: /clr  
void __stdcall f( System::String^ arg ) {}   // C4439  
void __clrcall f2( System::String^ arg ) {}   // OK  
void f3( System::String^ arg ) {}   // OK  
```