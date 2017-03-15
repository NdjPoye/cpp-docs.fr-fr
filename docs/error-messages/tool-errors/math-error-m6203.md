---
title: "Erreur math&#233;matique M6203 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "M6203"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "M6203"
ms.assetid: bd7fdd1c-83e4-4d6a-901e-10a0308bf5be
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur math&#233;matique M6203
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : \_OVERFLOW error  
  
 Le résultat de la fonction donnée était trop grand pour être représenté.  
  
 Cette erreur appelle la fonction `_matherr` avec le nom de la fonction, ses arguments et le type d'erreur.  Vous pouvez réécrire la fonction `_matherr` pour personnaliser la gestion de certaines erreurs mathématiques à virgule flottante survenant au moment de l'exécution.