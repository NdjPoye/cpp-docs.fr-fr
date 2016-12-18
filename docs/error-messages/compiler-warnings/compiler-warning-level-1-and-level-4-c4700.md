---
title: "Avertissement du compilateur (niveaux&#160;1 et 4) C4700 | Microsoft Docs"
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
  - "C4700"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4700"
ms.assetid: 2da0deb4-77dd-4b05-98d3-b78d74ac4ca7
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveaux&#160;1 et 4) C4700
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

variable locale 'nom' non initialisée utilisée  
  
 Vous avez utilisé la variable locale *nom* sans lui avoir préalablement assigné une valeur, ce qui peut donner lieu à des résultats imprévisibles.  
  
 L'exemple suivant génère l'erreur C4700 :  
  
```  
// C4700.cpp  
// compile with: /W1  
int main() {  
   int i;  
   return i;   // C4700  
}  
```  
  
 Sous [\/clr:safe](../../build/reference/clr-common-language-runtime-compilation.md), il s'agit d'un avertissement de niveau 4.  L'exemple suivant génère l'erreur C4700 :  
  
```  
// C4700b.cpp  
// compile with: /W4 /clr:safe /c  
using namespace System;  
int main() {  
   Int32^ bi;  
   return *bi;   // C4700  
}  
```