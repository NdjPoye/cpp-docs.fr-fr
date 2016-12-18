---
title: "Avertissement du compilateur (niveau 1) C4098 | Microsoft Docs"
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
  - "C4098"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4098"
ms.assetid: 8c8aef1c-1639-44ec-a3dd-c0dfe9aa727d
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4098
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : fonction 'void' retournant une valeur  
  
 Une fonction déclarée avec un type de retour [void](../../cpp/void-cpp.md) a une instruction `return` qui retourne une valeur.  Le compilateur suppose que la fonction retourne une valeur de type `int`.