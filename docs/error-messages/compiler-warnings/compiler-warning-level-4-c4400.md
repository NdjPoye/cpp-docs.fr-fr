---
title: "Avertissement du compilateur (niveau 4) C4400 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4400"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4400"
ms.assetid: f135fe98-4f92-4e07-9d71-2621b36ee755
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# Avertissement du compilateur (niveau 4) C4400
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : les qualificateurs const\/volatile pour ce type ne sont pas pris en charge  
  
 Les qualificateurs [const](../../cpp/const-cpp.md) et [volatile](../../cpp/volatile-cpp.md) ne fonctionnent pas avec des variables des types du Common Language Runtime.  
  
## Exemple  
 L'exemple suivant génère l'erreur C4400 :  
  
```  
// C4400.cpp  
// compile with: /clr /W4  
// C4401 expected  
using namespace System;  
#pragma warning (disable : 4101)  
int main() {  
   const String^ str;   // C4400  
   volatile String^ str2;   // C4400  
}  
```