---
title: "Erreur du compilateur C3205 | Microsoft Docs"
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
  - "C3205"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3205"
ms.assetid: 802d306e-5ff3-4491-8a22-c5f1c072d005
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3205
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La liste des arguments pour le paramètre template 'paramètre' du modèle est manquante  
  
 Un paramètre [template](../Topic/Template%20Specifications.md) est manquant.  
  
 L’exemple suivant génère l’erreur C3205 :  
  
```  
// C3205.cpp template<template<class> class T> struct A { typedef T unparameterized_type;   // C3205 // try the following line instead // typedef T<int> unparameterized_type; }; template <class T> struct B { typedef int value_type; }; int main() { A<B> x; }  
```