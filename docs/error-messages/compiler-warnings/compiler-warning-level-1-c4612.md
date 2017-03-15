---
title: "Avertissement du compilateur (niveau&#160;1) C4612 | Microsoft Docs"
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
  - "C4612"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4612"
ms.assetid: 21ac02b2-51cd-4aff-9b70-d543511d5962
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1) C4612
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

erreur dans le nom de fichier Include  
  
 Cet avertissement se produit avec **\#pragma include\_alias** quand un nom de fichier est incorrect ou manquant.  
  
 Les arguments de l’instruction **\#pragma include\_alias** peuvent utiliser les guillemets de \(**"***nom\_fichier***"**\) ou les crochets pointus de \(**\<***nom\_fichier***\>**\), mais les deux doivent utiliser la même forme.  
  
## Exemple  
  
```  
// C4612.cpp // compile with: /W1 /LD #pragma include_alias("StandardIO", <stdio.h>) // C4612  
```