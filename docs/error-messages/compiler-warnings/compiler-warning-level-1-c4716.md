---
title: "Avertissement du compilateur (niveau 1) C4716 | Microsoft Docs"
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
  - "C4716"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4716"
ms.assetid: d95ecfe5-870f-461f-a746-7913af98414b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4716
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' doit retourner une valeur  
  
 La fonction donnée n'a pas retourné de valeur.  
  
 Seules les fonctions avec un type de retour void peuvent utiliser la commande return sans valeur de retour associée.  
  
 Une valeur indéfinie sera retournée lors d'un appel de cette fonction.  
  
 Cet avertissement est automatiquement transformé en erreur.  Si vous souhaitez modifier ce comportement, utilisez [\#pragma warning](../../preprocessor/warning.md).  
  
 L'exemple suivant génère l'erreur C4716 :  
  
```  
// C4716.cpp  
// compile with: /c /W1  
// C4716 expected  
#pragma warning(default:4716)  
int test() {  
   // uncomment the following line to resolve  
   // return 0;  
}  
```