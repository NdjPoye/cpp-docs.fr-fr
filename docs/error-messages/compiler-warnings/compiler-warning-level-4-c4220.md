---
title: "Avertissement du compilateur (niveau 4) C4220 | Microsoft Docs"
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
  - "C4220"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4220"
ms.assetid: aba18868-825f-4763-9af6-3296406a80e4
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 4) C4220
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

varargs correspond aux paramètres restants  
  
 Sous les extensions Microsoft par défaut \(\/Ze\), un pointeur vers une fonction correspond à un pointeur vers une fonction d'arguments similaires mais variables.  
  
## Exemple  
  
```  
// C4220.c  
// compile with: /W4  
  
int ( *pFunc1) ( int a, ... );  
int ( *pFunc2) ( int a, int b);  
  
int main()  
{  
   if ( pFunc1 != pFunc2 ) {};  // C4220  
}  
```  
  
 Ces pointeurs ne correspondent pas sous compatibilité ANSI \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\).