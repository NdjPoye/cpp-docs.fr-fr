---
title: "Avertissement du compilateur (niveau 1) C4276 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4276"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4276"
ms.assetid: 9d738c2d-29e5-408a-b9ff-be1a850b2238
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement du compilateur (niveau 1) C4276
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : aucun prototype fourni ; aucun paramètre pris par défaut  
  
 Quand vous prenez l'adresse d'une fonction avec la convention d'appel [\_\_stdcall](../../cpp/stdcall.md), vous devez donner un prototype afin que le compilateur puisse créer le nom décoré de la fonction.  Comme *fonction* n'a pas de prototype, le compilateur, lors de la création du nom décoré, suppose que la fonction n'a pas de paramètre.