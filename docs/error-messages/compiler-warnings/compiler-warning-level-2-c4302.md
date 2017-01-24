---
title: "Avertissement du compilateur (niveau 2) C4302 | Microsoft Docs"
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
  - "C4302"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4302"
ms.assetid: f5e1c939-e134-4cca-ba1e-9b15a81549ae
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 2) C4302
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'conversion' : troncation de 'type 1' à 'type 2'  
  
 Le compilateur a détecté une conversion d'un type vers un type plus petit.  Une perte d'informations est possible.  
  
 Cet avertissement est désactivé par défaut.  Pour plus d'informations, consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 L'exemple suivant génère l'erreur C4302 :  
  
```  
// C4302.cpp  
// compile with: /W2  
#pragma warning(default : 4302)  
int main() {  
   int i;  
   char c = (char) &i;     // C4302  
   short s = (short) &i;   // C4302  
}  
```