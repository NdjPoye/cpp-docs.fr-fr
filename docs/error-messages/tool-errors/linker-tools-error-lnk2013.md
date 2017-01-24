---
title: "Erreur des outils &#201;diteur de liens LNK2013 | Microsoft Docs"
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
  - "LNK2013"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2013"
ms.assetid: 21408e2d-3f56-4d1f-a031-00df70785ed4
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur des outils &#201;diteur de liens LNK2013
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dépassement de la correction type\_de\_correction.Cible 'nom de symbole' hors limites  
  
 L'éditeur de liens ne peut pas faire tenir l'adresse ou le décalage nécessaire dans l'instruction donnée parce que le symbole cible est trop loin de l'emplacement de l'instruction.  
  
 Vous pouvez résoudre ce problème en créant plusieurs images ou en utilisant l'option [\/ORDER](../../build/reference/order-put-functions-in-order.md) pour rapprocher l'instruction de la cible.  
  
 Lorsque le nom du symbole désigne un symbole défini par l'utilisateur \(et non généré par le compilateur\), vous pouvez également tenter les actions suivantes pour corriger l'erreur :  
  
-   Modifiez la fonction statique en non statique.  
  
-   Renommez la section de code contenant la fonction statique avec le même nom que l'appelant.  
  
 Utilisez `DUMPBIN /SYMBOLS` pour déterminer si une fonction est statique.