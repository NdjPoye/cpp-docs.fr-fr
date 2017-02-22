---
title: "Erreur du compilateur C2692 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2692"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2692"
ms.assetid: 02ade3b4-b757-448b-b065-d7d71bc3f441
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Erreur du compilateur C2692
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'nom\_fonction' : fonctions entièrement prototypées requises dans le compilateur C avec l'option '\/clr'  
  
 Lorsque vous effectuez la compilation d'un code managé .NET, le compilateur C requiert des déclarations de fonction ANSI.  De plus, si une fonction n'accepte aucun paramètre, il faut explicitement déclarer le type de paramètre comme `void`.