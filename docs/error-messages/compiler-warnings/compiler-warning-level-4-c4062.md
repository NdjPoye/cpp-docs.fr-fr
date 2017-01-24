---
title: "Avertissement du compilateur (niveau&#160;4) C4062 | Microsoft Docs"
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
  - "C4062"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4062"
ms.assetid: 36d1c6ae-c917-4b08-bf30-2eb49ee94169
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;4) C4062
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

l’énumérateur 'identificateur' dans un switch de l’enum 'énumération' n'est pas géré  
  
 L’énumération n’a pas de handler associé dans une instruction `switch` et il n’existe aucune étiquette **par défaut**.  
  
 Cet avertissement est désactivé par défaut. Consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md) pour plus d'informations.  
  
 L’exemple suivant génère l’avertissement C4062 :  
  
```  
// C4062.cpp // compile with: /W4 #pragma warning(default : 4062) enum E { a, b, c }; void func ( E e ) { switch(e) { case a: case b: break;   // no default label }   // C4062, enumerate 'c' not handled } int main() { }  
```