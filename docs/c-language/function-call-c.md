---
title: "Appel de fonction (C) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "appels de fonction"
  - "appels de fonction, fonctions C"
  - "fonctions (C), appeler"
ms.assetid: 35c66719-3f15-4d3b-97da-4e19dc97b308
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Appel de fonction (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un appel de fonction est une expression qui inclut le nom de la fonction appelée ou la valeur d'un pointeur fonction et, éventuellement, les arguments passés à la fonction.  
  
## Syntaxe  
 *postfix\-expression* :  
 *postfix\-expression*  **\(**  *argument\-expression\-list*  opt **\)**  
  
 *argument\-expression\-list* :  
 *assignment\-expression*  
  
 *argument\-expression\-list*  **,**  *assignment\-expression*  
  
 *postfix\-expression* doit prendre la valeur d'une adresse de fonction \(par exemple, un identificateur de fonction ou la valeur d'un pointeur fonction\), et *argument\-expression\-list* est une liste d'expressions \(séparées par des virgules\) dont les valeurs \(les arguments\) sont passées à la fonction.  L'argument *argument\-expression\-list* peut être vide.  
  
 Une expression de fonction d'appel a la valeur et le type de la valeur de retour de la fonction.  Une fonction ne peut pas retourner d'objet de type tableau.  Si le type de retour de la fonction est `void` \(autrement dit si la fonction n'a jamais été déclarée pour retourner une valeur\), l'expression d'appel de fonction a également le type `void`. \(Pour plus d'informations, consultez [Appels de fonction](../c-language/function-calls.md).\)  
  
## Voir aussi  
 [Opérateur d'appel de fonction : \(\)](../cpp/function-call-operator-parens.md)