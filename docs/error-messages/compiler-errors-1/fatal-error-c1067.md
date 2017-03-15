---
title: "Erreur irr&#233;cup&#233;rable C1067 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1067"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1067"
ms.assetid: e2c94be6-4573-4571-aac9-73d657fe9f96
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur irr&#233;cup&#233;rable C1067
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

limite du compilateur : un enregistrement de type a dépassé la taille maximale de 64 Ko  
  
 Cette erreur peut apparaître si un symbole comporte un nom décoré dépassant 247 caractères.  Pour y remédier, raccourcissez le nom du symbole.  
  
 Lorsque le compilateur génère des informations de débogage, il émet des enregistrements de type pour définir les types rencontrés dans le code source.  Par exemple, les enregistrements de type incluent des listes de structures et d'arguments simples de fonctions.  Certains de ces enregistrements de type peuvent être de longues listes.  
  
 La taille de tout enregistrement de type est limitée à 64 Ko.  Si cette limite de 64 K  est dépassée, cette erreur se produit.  
  
 L'erreur C1067 peut aussi se produire s'il existe de  trop nombreux symboles avec des noms longs ou si une classe, structure ou union comporte trop de membres.