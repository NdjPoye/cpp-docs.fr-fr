---
title: "Erreur du compilateur C2758 | Microsoft Docs"
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
  - "C2758"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2758"
ms.assetid: 1d273034-194c-4926-9869-142d1b219cbe
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2758
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'membre' : un membre de type référence const doit être initialisé  
  
 L'erreur du compilateur C2758 survient quand le constructeur n'initialise pas un membre du type de référence dans une liste d'initialiseurs.  Le compilateur laisse le membre non défini.  Les variables du membre de référence doivent être initialisées quand elles sont déclarées ou se voir attribuer une valeur dans la liste d'initialisation du constructeur.  
  
 L'exemple suivant génère l'erreur C2758 :  
  
```  
// C2758.cpp  
// Compile by using: cl /W3 /c C2758.cpp  
struct A {  
   const int i;  
  
   A(int n) { };   // C2758  
   // try the following line instead  
   // A(int n) : i{n} {};  
};  
```