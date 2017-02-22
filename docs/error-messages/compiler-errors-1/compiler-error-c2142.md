---
title: "Erreur du compilateur C2142 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2142"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2142"
ms.assetid: d0dbe10e-0952-49a4-8b33-e82fb7558b19
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C2142
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

déclarations de fonction différentes, paramètres de variables spécifiés seulement dans l'une d'entre elles  
  
 Une déclaration de la fonction contient une liste de paramètres de variables.  Une autre déclaration n'en contient pas.  C ANSI \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) seulement.  
  
 L'exemple suivant génère l'erreur C2142 :  
  
```  
// C2142.c  
// compile with: /Za /c  
void func();  
void func( int, ... );   // C2142  
void func2( int, ... );   // OK  
```