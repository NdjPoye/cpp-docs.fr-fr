---
title: "Erreur du compilateur C3289 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3289"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3289"
ms.assetid: 3c1c623b-7fcf-43ab-a89a-8722532a8d29
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur du compilateur C3289
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'property' : une propriété triviale ne peut pas être indexée  
  
 Une propriété n’a pas été correctement déclarée. Les accesseurs doivent être définis pour une propriété indexée. Pour plus d’informations, consultez [property](../../windows/property-cpp-component-extensions.md).  
  
## Exemple  
 L’exemple suivant génère l’erreur C3289.  
  
```  
// C3289.cpp // compile with: /clr public ref struct C { // user-defined simple indexer property int indexer1[int];   // C3289 // user-defined indexer property int indexer2[int] { int get(int i) { return 0; } void set(int i, int j) {} } }; int main() { C ^ MyC = gcnew C(); MyC->indexer2[0] = 1; }  
```