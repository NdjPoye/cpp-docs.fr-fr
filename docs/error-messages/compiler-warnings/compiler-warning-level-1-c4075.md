---
title: "Avertissement du compilateur (niveau&#160;1) C4075 | Microsoft Docs"
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
  - "C4075"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4075"
ms.assetid: 19a700b6-f210-4b9d-a2f2-76cfe39ab178
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1) C4075
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

initialiseurs placés dans une zone d'initialisation non reconnue  
  
 Un [\#pragma init\_seg](../../preprocessor/init-seg.md) utilise un nom de section non reconnu. Le compilateur ignore la commande **pragma**.  
  
 L’exemple suivant génère l’avertissement C4075 :  
  
```  
// C4075.cpp // compile with: /W1 #pragma init_seg("mysegg")   // C4075 // try.. // #pragma init_seg(user) int main() { }  
```