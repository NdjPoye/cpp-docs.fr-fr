---
title: "Avertissement du compilateur (niveau 1) C4526 | Microsoft Docs"
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
  - "C4526"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4526"
ms.assetid: 490f8916-5fdc-4cad-b412-76c3382a5976
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4526
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : les fonctions membre static ne peuvent pas substituer la fonction virtual 'fonction virtuelle' substitution ignorée, la fonction virtual sera masquée  
  
 La fonction membre statique correspond aux critères de substitution de la fonction virtuelle, ce qui rend la fonction membre à la fois virtuelle et statique.  
  
 Le code suivant génère C4526 :  
  
```  
// C4526.cpp  
// compile with: /W1 /c  
// C4526 expected  
struct myStruct1 {  
   virtual void __stdcall func( int ) = 0;  
};  
  
struct myStruct2: public myStruct1 {  
   static void __stdcall func( int );  
};  
```  
  
 Voici des corrections possibles :  
  
-   Si la fonction était destinée à substituer une fonction virtuelle d'une classe de base, supprimez le spécificateur statique.  
  
-   Si la fonction était destinée à être une fonction membre statique, renommez\-la pour qu'elle ne fasse plus conflit avec la fonction virtuelle de la classe de base.