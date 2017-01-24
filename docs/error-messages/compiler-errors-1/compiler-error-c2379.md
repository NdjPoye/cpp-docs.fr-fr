---
title: "Erreur du compilateur C2379 | Microsoft Docs"
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
  - "C2379"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2379"
ms.assetid: 37dc3015-a4af-4341-bbf3-da6150df7e51
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2379
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

le paramètre formel 'numéro' a un type différent lors de sa promotion  
  
 Le type du paramètre spécifié n'est pas compatible, via les promotions par défaut, avec le type d'une déclaration précédente.  Ceci est une erreur en C ANSI \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) et un avertissement avec les extensions Microsoft \(**\/Ze**\).  
  
 L'exemple suivant génère l'erreur C2379 :  
  
```  
// C2379.c  
// compile with: /Za  
void func();  
void func(char);   // C2379, char promotes to int  
```