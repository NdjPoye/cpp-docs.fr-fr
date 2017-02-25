---
title: "Sp&#233;cialisation explicite de mod&#232;les de fonctions | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "déclarer des fonctions, spécialisation du modèle de fonction"
  - "spécialisation explicite des modèles de fonctions"
  - "modèles de fonctions, spécialisation"
  - "substituer, fonctions"
  - "spécialisation des modèles de fonction"
ms.assetid: eb0fcb73-eaed-42a1-9b83-14b055a34bf8
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Sp&#233;cialisation explicite de mod&#232;les de fonctions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Avec un modèle de fonction, vous pouvez définir un comportement spécial pour un type spécifique en fournissant une spécialisation explicite \(substitution\) du modèle de fonction pour ce type.  Par exemple :  
  
```  
template<> void MySwap(double a, double b);  
```  
  
 Cette déclaration vous permet de définir une fonction différente pour les variables **double**.  Comme les fonctions sans modèle, les conversions de type standard \(comme la promotion d'une variable de type **float** en **double**\) sont appliquées.  
  
## Exemple  
  
```  
// explicit_specialization.cpp  
template<class T> void f(T t)  
{  
};  
  
// Explicit specialization of f with 'char' with the  
// template argument explicitly specified:  
//  
template<> void f<char>(char c)  
{  
}  
  
// Explicit specialization of f with 'double' with the  
// template argument deduced:  
//  
template<> void f(double d)  
{  
}  
int main()  
{  
}  
```  
  
## Voir aussi  
 [Modèles de fonctions](../cpp/function-templates.md)