---
title: "Avertissement du compilateur (niveau 1) C4172 | Microsoft Docs"
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
  - "C4172"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4172"
ms.assetid: a8d2bf65-d8b1-4fe3-8340-a223d7e7fde6
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4172
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

retourne l'adresse d'une variable locale ou temporaire  
  
 Une fonction retourne l'adresse d'une variable locale ou d'un objet temporaire.  Les variables locales et objets temporaires sont détruits au retour d'une fonction, donc l'adresse retournée n'est pas valide.  
  
 Revoyez la conception de la fonction afin qu'elle ne retourne pas l'adresse d'un objet local.  
  
 L'exemple suivant génère l'erreur C4172 :  
  
```  
// C4172.cpp  
// compile with: /W1 /LD  
float f = 10;  
  
const double& bar() {  
// try the following line instead  
// const float& bar() {  
   return f;   // C4172  
}  
```