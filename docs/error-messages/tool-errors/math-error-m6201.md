---
title: "Erreur math&#233;matique M6201 | Microsoft Docs"
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
  - "M6201"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "M6201"
ms.assetid: 4041c331-d9aa-4dd4-b565-7dbe0218538c
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur math&#233;matique M6201
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : erreur \_DOMAIN  
  
 Un argument de la fonction ne faisait pas partie de la plage des valeurs d'entrée valides de cette fonction.  
  
## Exemple  
  
```  
result = sqrt(-1.0)   // C statement  
result = SQRT(-1.0)   !  FORTRAN statement  
```  
  
 Cette erreur appelle la fonction `_matherr` avec le nom de la fonction, ses arguments et le type d'erreur.  Vous pouvez réécrire la fonction `_matherr` pour personnaliser la gestion de certaines erreurs mathématiques à virgule flottante survenant au moment de l'exécution.