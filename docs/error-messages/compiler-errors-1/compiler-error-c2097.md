---
title: "Erreur du compilateur C2097 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2097"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2097"
ms.assetid: 7e5b2fd4-f61c-4b8a-b265-93e987a04bd3
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur du compilateur C2097
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

initialisation non conforme  
  
### Pour résoudre le problème en vérifiant les causes possibles suivantes  
  
1.  Initialisation d'une variable avec une valeur non constante.  
  
2.  Initialisation d'une adresse courte avec une adresse longue.  
  
3.  Initialisation d'une structure, d'une union ou d'un tableau local\(e\) avec une expression non constante lors de la compilation avec **\/Za**.  
  
4.  Initialisation avec une expression contenant un opérateur à virgule.  
  
5.  Initialisation avec une expression ni constante ni symbolique.