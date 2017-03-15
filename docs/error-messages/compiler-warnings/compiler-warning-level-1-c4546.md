---
title: "Avertissement du compilateur (niveau 1) C4546 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4546"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4546"
ms.assetid: 071e1709-3841-46c1-8e71-96109cd22041
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Avertissement du compilateur (niveau 1) C4546
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

l'appel de fonction avant la virgule n'a pas de liste d'arguments  
  
 Le compilateur a détecté une expression avec virgules incorrecte.  
  
 Cet avertissement est désactivé par défaut.  Pour plus d'informations, consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C4546 :  
  
```  
// C4546.cpp  
// compile with: /W1  
#pragma warning (default : 4546)  
void f(int i) {  
   i++;  
}  
  
int main() {  
   int i = 0, k = 0;  
  
   if ( f, k )   // C4546  
   // try the following line instead  
   // if ( f(i), k )  
      i++;  
}  
```