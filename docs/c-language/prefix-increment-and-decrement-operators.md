---
title: "Op&#233;rateurs pr&#233;fix&#233;s d&#39;incr&#233;mentation et de d&#233;cr&#233;mentation | Microsoft Docs"
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
  - "opérateurs de décrémentation"
  - "opérateurs de décrémentation, syntaxe"
  - "opérateur d'incrémentation, types de"
ms.assetid: 9a441bb9-d94a-4b6a-9db2-0d0d76bc480d
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateurs pr&#233;fix&#233;s d&#39;incr&#233;mentation et de d&#233;cr&#233;mentation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les opérateurs unaires \(`++` et **––**\) sont appelés opérateurs d'incrémentation ou de décrémentation « préfixés » lorsqu'ils apparaissent avant l'opérande.  L'incrémentation et la décrémentation suffixées ont une priorité plus élevée que l'incrémentation et la décrémentation préfixées.  L'opérande doit être de type entier, flottant ou pointeur et doit être une expression lvalue modifiable \(une expression sans l'attribut **const** \).  Le résultat est une l\-value.  
  
 Lorsque l'opérateur apparaît avant son opérande, l'opérande est incrémenté ou décrémenté et sa nouvelle valeur est le résultat de l'expression.  
  
 Un opérande de type intégral ou virgule flottante est incrémenté ou décrémenté par la valeur 1 entière.  Le type du résultat est identique au type d'opérande.  Un opérande de type pointeur est incrémenté ou décrémenté par la taille de l'objet qu'il adresse.  Un pointeur incrémenté pointe vers l'objet suivant. Un pointeur décrémenté pointe vers l'objet précédent.  
  
## Exemple  
 Cet exemple illustre l'opérateur de pré\-décrémentation unaire :  
  
```  
if( line[--i] != '\n' )  
    return;  
```  
  
 Dans cet exemple, la variable `i` est décrémentée avant d'être utilisée comme indice sur `line`.  
  
## Voir aussi  
 [Opérateurs unaires C](../c-language/c-unary-operators.md)