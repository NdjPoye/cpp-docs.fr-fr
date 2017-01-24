---
title: "Erreur du compilateur C2466 | Microsoft Docs"
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
  - "C2466"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2466"
ms.assetid: 75b251d1-7d0b-4a86-afca-26adedf74486
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2466
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible d'allouer un tableau de constantes de taille 0  
  
 Un tableau est alloué ou déclaré avec la taille zéro.  L'expression constante pour la taille du tableau doit être un entier supérieur à zéro.  Une déclaration de tableau avec un indice zéro est reconnue uniquement pour un membre de classe, de structure ou d'union ayant les extensions Microsoft \([\/Ze](../../build/reference/za-ze-disable-language-extensions.md)\).  
  
 L'exemple suivant génère l'erreur C2466 :  
  
```  
// C2466.cpp  
// compile with: /c  
int i[0];   // C2466  
int j[1];   // OK  
char *p;  
```