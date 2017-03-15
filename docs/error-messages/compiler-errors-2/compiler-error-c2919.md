---
title: "Compiler Error C2919 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2919"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2919"
ms.assetid: 140a6db9-eb48-4c5e-84a7-a09d2653605b
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Compiler Error C2919
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : les opérateurs ne peuvent pas être utilisés sur la surface publiée d'un type WinRT  
  
 Le système de type Windows Runtime ne prend pas en charge les fonctions membres d'opérateur dans la surface publiée d'un type.  Cela est dû au fait que tous les langages ne peuvent pas consommer les fonctions membres d'opérateur.  Vous pouvez créer des fonctions membres d'opérateur privé ou interne qui peuvent être appelées à partir du code C\+\+ dans la même unité de compilation ou de classe.  
  
 Pour résoudre ce problème, supprimez la fonction membre de l'opérateur à partir de l'interface publique, ou remplacez\-la par une fonction membre nommée.  Par exemple, à la place de `operator==`, nommez la fonction membre `Equals`.