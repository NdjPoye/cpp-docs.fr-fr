---
title: "Erreur du compilateur C3200 | Microsoft Docs"
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
  - "C3200"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3200"
ms.assetid: 44bb5e77-f0ec-421c-a732-b9ee7c0a3529
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3200
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'modèle' : argument template non valide pour le paramètre de modèle 'paramètre', modèle de classe attendu  
  
 Vous avez passé un argument non valide pour un modèle de classe.  Le modèle de classe attend modèle comme paramètre.  Dans l'exemple suivant, l'appel à `Y<int, int> aY` génère l'erreur C3200.  Le premier paramètre doit être un modèle, par exemple `Y<X, int> aY`.  
  
```  
// C3200.cpp  
template<typename T>  
class X  
{  
};  
  
template<template<typename U> class T1, typename T2>  
class Y  
{  
};  
  
int main()  
{  
   Y<int, int> y;   // C3200  
}  
```