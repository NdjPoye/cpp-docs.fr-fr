---
title: "Avertissement du compilateur (niveaux 1 et 4) C4115 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4115"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4115"
ms.assetid: f3f94e72-fc49-4d09-b3e7-23d68e61152f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement du compilateur (niveaux 1 et 4) C4115
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : définition d’un type nommé dans les parenthèses  
  
 Le symbole donné est utilisé pour définir une structure, une union ou un type énuméré dans une expression entre parenthèses. La portée de la définition peut être inattendue.  
  
 Dans un appel de fonction C, la définition a une portée globale. Dans un appel C\+\+, la définition a la même portée que la fonction appelée.  
  
 Cet avertissement peut également être dû à des déclarateurs entre parenthèses \(tels que des prototypes\) qui ne sont pas des expressions entre parenthèses.  
  
 Il s’agit d’un avertissement de niveau 1 avec les programmes C\+\+ et les programmes C compilés sous compatibilité ANSI \(\/Za\). Sinon, il s’agit d’un avertissement de niveau 3.