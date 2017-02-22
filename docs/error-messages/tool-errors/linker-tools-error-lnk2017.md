---
title: "Erreur des outils &#201;diteur de liens LNK2017 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2017"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2017"
ms.assetid: f7c21733-b0fb-4888-a295-9b453ba6ee77
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur des outils &#201;diteur de liens LNK2017
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

réadressage de 'symbole' vers 'segment' non valide sans \/LARGEADDRESSAWARE:NO  
  
 Vous tentez de générer une image 64 bits avec des adresses 32 bits.  Pour cela, vous devez :  
  
-   Utiliser une adresse de chargement fixe.  
  
-   Restreindre l'image à 3 Go.  
  
-   Spécifier [\/largeaddressaware:no](../../build/reference/largeaddressaware-handle-large-addresses.md).