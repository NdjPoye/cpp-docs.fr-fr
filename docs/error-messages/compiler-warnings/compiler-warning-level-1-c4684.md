---
title: "Avertissement du compilateur (niveau 1) C4684 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4684"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4684"
ms.assetid: e95f1a83-2784-4b05-ae94-12148e056e26
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement du compilateur (niveau 1) C4684
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

l'attribut 'attribute' : AVERTISSEMENT\!\! peut entraîner une génération de code invalide : à utiliser avec prudence  
  
 Vous avez utilisé un attribut qui ne devrait pas être utilisé couramment.  
  
 L'exemple suivant génère l'erreur C4684 :  
  
```  
// C4684.cpp  
// compile with: /W1 /LD  
 [module(name="xx")]; // C4684 expected  
[no_injected_text];  
```