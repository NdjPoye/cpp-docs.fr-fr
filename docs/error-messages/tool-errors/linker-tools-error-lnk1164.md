---
title: "Erreur des outils &#201;diteur de liens LNK1164 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1164"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1164"
ms.assetid: da89765c-affa-4f88-b170-6d6b19a577cf
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur des outils &#201;diteur de liens LNK1164
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

pour la section 'section', l'alignement \(numéro\) est supérieur à la valeur \/ALIGN  
  
 La taille d'alignement pour la section donnée dans le fichier objet dépasse la valeur spécifiée avec l'option [\/ALIGN](../../build/reference/align-section-alignment.md).  La valeur **\/ALIGN** doit être une puissance de 2 égale ou supérieure à l'alignement de section donné dans le fichier objet.  
  
 Vous pouvez soit recompiler avec un alignement de section plus petit, soit augmenter la valeur **\/ALIGN**.