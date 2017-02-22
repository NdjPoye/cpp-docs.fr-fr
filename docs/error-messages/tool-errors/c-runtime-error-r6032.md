---
title: "R6032 d’erreur d’ex&#233;cution C | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6032"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6032"
ms.assetid: 52092a63-cc51-444a-bfc3-fad965a3558e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur d&#39;ex&#233;cution C R6032
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Espace insuffisant pour les informations relatives aux paramètres régionaux  
  
 Le runtime conserve les informations relatives aux paramètres régionaux sur chaque thread afin de pouvoir traiter les appels de fonctions sensibles aux paramètres régionaux.  Si l'allocation de la mémoire pour ces informations échoue, le runtime est incapable de poursuivre car un trop grand nombre de ses services de base en dépendent.