---
title: "Erreur du compilateur C2111 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2111"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2111"
ms.assetid: 38fd42ec-1480-4a44-aaca-ae4593ed5f50
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2111
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\+' : l’addition d’un pointeur exige un opérande de type entier  
  
 Une tentative a été effectuée d’ajouter une valeur non entière à un pointeur avec l’opérateur plus \(`+`\).  
  
 L’exemple suivant génère l’erreur C2111 :  
  
```  
// C2111.cpp int main() { int *a = 0, *pa = 0, b = 0; double d = 0.00; a = pa + d;   // C2111 a = pa + b;   // OK }  
```