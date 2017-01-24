---
title: "Erreur du compilateur C3771 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3771"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3771"
ms.assetid: 68c23b25-7f21-4eaa-8f7e-38fda1130a69
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3771
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"identifier" : déclaration friend introuvable dans la portée espace de noms la plus proche  
  
 La déclaration de modèle de classe pour le modèle spécifié *identifier* est introuvable dans l’espace de noms actuel.  
  
### Pour corriger cette erreur  
  
-   Assurez\-vous que la déclaration de modèle de classe pour l’identificateur de modèle est définie dans l’espace de noms actuel ou que l’identificateur de modèle est un nom complet.  
  
## Exemple  
 L’exemple de code suivant déclare un modèle de classe et une fonction dans l’espace de noms `NA`, mais tente de déclarer un modèle de fonction friend dans l’espace de noms `NB`.  
  
```  
// C3771.cpp // compile with: /c namespace NA { template<class T> class A { void aFunction(T t) {}; }; } // using namespace NA; namespace NB { class X { template<class T> friend void A<T>::aFunction(T); // C3771 // try the following line instead //      template<class T> friend void NA::A<T>::aFunction(T); // or try "using namespace NA;" instead. }; }  
```  
  
## Voir aussi  
 [Spécifications de modèle](../Topic/Template%20Specifications.md)