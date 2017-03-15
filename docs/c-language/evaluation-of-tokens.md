---
title: "&#201;valuation des jetons | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "jetons, évaluer"
ms.assetid: 28870b62-dff6-4644-8b75-d58f340b48d2
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# &#201;valuation des jetons
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque le compilateur interprète les jetons, il inclut autant de caractères que possible dans un jeton avant de passer au jeton suivant.  En raison de ce comportement, le compilateur peut ne pas interpréter les jetons comme prévu, s'ils ne sont pas correctement séparés par des espaces blancs.  Prenons l'expression suivante :  
  
```  
i+++j  
```  
  
 Dans cet exemple, le compilateur commence par créer l'opérateur le plus long possible \(`++`\) à partir des trois signes plus, puis traite le signe plus restant comme opérateur d'addition \(`+`\).  Ainsi, l'expression est interprétée comme `(i++) + (j)`, et non pas comme `(i) + (++j)`.  Dans ce cas et des cas similaires, utilisez des espaces blancs et des parenthèses pour éviter toute ambiguïté et garantir l'évaluation de l'expression appropriée.  
  
 **Section spécifique à Microsoft**  
  
 Le compilateur C traite un caractère CTRL\+Z comme un indicateur de fin de fichier.  Il ignore le texte après CTRL\+Z.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Jetons C](../c-language/c-tokens.md)