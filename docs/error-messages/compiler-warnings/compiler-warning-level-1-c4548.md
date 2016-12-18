---
title: "Avertissement du compilateur (niveau 1) C4548 | Microsoft Docs"
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
  - "C4548"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4548"
ms.assetid: 2cee817e-e463-4d90-bbd2-de120d48c101
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4548
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

l'expression avant la virgule n'a pas d'effet ; expression avec effet secondaire attendu  
  
 Le compilateur a détecté une expression avec virgules incorrecte.  
  
 Cet avertissement est désactivé par défaut.  Pour plus d'informations, consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 L'exemple suivant génère l'erreur C4548 :  
  
```  
// C4548.cpp  
// compile with: /W1  
#pragma warning (default : 4548)  
int main()  
{  
   int i = 0, k = 0;  
  
   if ( i, k )   // C4548  
   // try the following line instead  
   // if ( i = 0, k )  
      i++;  
}  
```