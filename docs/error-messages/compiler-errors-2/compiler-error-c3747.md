---
title: "Erreur du compilateur C3747 | Microsoft Docs"
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
  - "C3747"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3747"
ms.assetid: a9a4be67-5d9c-4dcc-9ae9-baae46cbecde
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3747
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

paramètre type par défaut manquant : paramètre 'param'  
  
 Les paramètres génériques ou de modèle ayant des valeurs par défaut ne peuvent pas être suivis, dans la liste de paramètres, par des paramètres qui n'ont pas de valeurs par défaut.  
  
 L'exemple suivant génère l'erreur C3747 :  
  
```  
// C3747.cpp  
template <class T1 = int, class T2>   // C3747  
struct MyStruct {};  
```  
  
 Résolution possible :  
  
```  
// C3747b.cpp  
// compile with: /c  
template <class T1, class T2 = int>  
struct MyStruct {};  
```