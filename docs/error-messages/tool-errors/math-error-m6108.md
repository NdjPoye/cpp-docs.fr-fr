---
title: "Erreur math&#233;matique M6108 | Microsoft Docs"
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
  - "M6108"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "M6108"
ms.assetid: 054893b4-49bc-45d9-882f-7cb50ba387c0
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur math&#233;matique M6108
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

racine carrée  
  
 La valeur de l'opérande était négative dans l'opération de calcul de la racine carrée.  
  
 Le programme se termine par le code de sortie 136.  
  
> [!NOTE]
>  La fonction `sqrt` de la bibliothèque Runtime C et la fonction intrinsèque FORTRAN **SQRT** ne génèrent pas cette erreur.  La fonction `sqrt` de C vérifie l'argument avant d'exécuter l'opération et retourne une valeur d'erreur si l'opérande est négatif.  La fonction FORTRAN **SQRT** génère l'erreur DOMAIN [M6201](../../error-messages/tool-errors/math-error-m6201.md) à la place de cette erreur.