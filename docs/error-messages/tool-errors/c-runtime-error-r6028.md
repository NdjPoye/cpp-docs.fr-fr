---
title: "R6028 d’erreur d’ex&#233;cution C | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6028"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6028"
ms.assetid: 81e99079-4388-4244-a4f7-4641c508871c
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur d&#39;ex&#233;cution C R6028
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible d'initialiser le tas  
  
 Cette erreur se produit lorsque le système d'exploitation ne parvient pas à créer le pool de mémoire pour l'application ;  plus particulièrement, CRT \(C Runtime\) a appelé la fonction Win32 `HeapCreate`, qui a retourné la valeur NULL, ce qui indique un échec.  
  
 Si cette erreur se produit au démarrage de l'application, le système n'est peut\-être pas en mesure de répondre aux requêtes de tas, en raison du chargement de pilotes défectueux.  Consultez le site Web Windows Update ou le site Web du fabricant de votre matériel pour obtenir des pilotes mis à jour.