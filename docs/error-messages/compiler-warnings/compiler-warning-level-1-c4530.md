---
title: "Avertissement du compilateur (niveau 1) C4530 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4530"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4530"
ms.assetid: a04dcdb2-84db-459d-9e5e-4e743887465f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Avertissement du compilateur (niveau 1) C4530
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gestionnaire d'exceptions C\+\+ utilisé, mais les sémantiques de déroulement n'ont pas été activées.Spécifiez \/EHsc  
  
 La gestion des exceptions C\+\+ a été utilisée, mais [\/EHsc](../../build/reference/eh-exception-handling-model.md) n'a pas été sélectionné.  
  
 Quand l'option \/EHsc n'a pas été activée, un objet à stockage automatique dans le frame ne sera pas détruit entre la levée de l'exception et la détection de l'exception par la fonction.  Mais un objet à stockage automatique créé dans un bloc **try** ou **catch** sera bien détruit.  
  
 L'exemple suivant génère l'erreur C4530 :  
  
```  
// C4530.cpp  
// compile with: /W1  
int main() {  
   try{} catch(int*) {}   // C4530  
}  
```  
  
 Compilez l'exemple avec \/EHsc pour remédier à cet avertissement.