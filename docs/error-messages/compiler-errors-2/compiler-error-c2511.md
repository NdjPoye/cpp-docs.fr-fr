---
title: "Erreur du compilateur C2511 | Microsoft Docs"
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
  - "C2511"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2511"
ms.assetid: df999efe-fe2b-418b-bb55-4af6a0592631
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2511
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : impossible de trouver la fonction membre surchargée dans 'classe'  
  
 Aucune version de la fonction n'est déclarée avec les paramètres spécifiés.  Causes possibles :  
  
1.  Paramètres erronés passés à la fonction.  
  
2.  Paramètres passés dans un ordre erroné.  
  
3.  Orthographe incorrecte dans les noms de paramètres.  
  
 L'exemple suivant génère l'erreur C2511 :  
  
```  
// C2511.cpp  
// compile with: /c  
class C {  
   int c_2;  
   int Func(char *, char *);  
};  
  
int C::Func(char *, char *, int i) {   // C2511  
// try the following line instead  
// int C::Func(char *, char *) {  
   return 0;  
}  
```