---
title: "Erreur du compilateur C2756 | Microsoft Docs"
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
  - "C2756"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2756"
ms.assetid: 42eb988d-4043-4dee-8fd4-596949f69a55
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2756
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type de modèle' : les arguments template par défaut ne sont pas autorisés sur une spécialisation partielle  
  
 Le modèle pour une spécialisation partielle ne peut pas contenir d'argument par défaut.  
  
 L'exemple suivant génère l'erreur C2756 et montre comment la corriger :  
  
```  
// C2756.cpp  
template <class T>  
struct S {};  
  
template <class T=int>  
// try the following line instead  
// template <class T>  
struct S<T*> {};   // C2756  
```