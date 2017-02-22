---
title: "Avertissement du compilateur (niveau 4) C4510 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4510"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4510"
ms.assetid: fd28d1d4-ad27-4dad-94c0-9dba46c93180
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement du compilateur (niveau 4) C4510
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe' : le constructeur par défaut n'a pas pu être généré  
  
 Le compilateur ne peut pas générer un constructeur par défaut pour la classe spécifiée et aucun constructeur défini par l'utilisateur n'a été créé.  Vous ne pourrez pas créer d'objet de ce type.  
  
 Plusieurs situations peuvent empêcher le compilateur de générer un constructeur par défaut, entre autres :  
  
-   Une donnée membre const.  
  
-   Une donnée membre qui est une référence.  
  
 Vous devez créer un constructeur par défaut défini par l'utilisateur pour la classe qui initialise ces membres.  
  
 L'exemple suivant génère l'erreur C4510 :  
  
```  
// C4510.cpp  
// compile with: /W4  
struct A {  
   const int i;  
   int &j;  
   A& operator=( const A& ); // C4510 expected  
   // uncomment the following line to resolve this C4510  
   // A(int ii, int &jj) : i(ii), j(jj) {}  
};   // C4510  
  
int main() {  
}  
```