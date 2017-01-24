---
title: "Erreur du compilateur C2055 | Microsoft Docs"
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
  - "C2055"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2055"
ms.assetid: 6cec79cc-6bec-443f-9897-fbf5452718c7
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2055
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

liste de paramètres formels attendue, non une liste de types  
  
 Une définition de fonction contient une liste de types de paramètres plutôt qu'une liste de paramètres formels.  C ANSI requiert l'attribution d'un nom aux paramètres formels, sauf s'ils sont du type void, ou remplacés par des points de suspension \(`...`\).  
  
 L'exemple suivant génère l'erreur C2055 :  
  
```  
// C2055.c  
// compile with: /c  
void func(int, char) {}  // C2055  
void func (int i, char c) {}   // OK  
```