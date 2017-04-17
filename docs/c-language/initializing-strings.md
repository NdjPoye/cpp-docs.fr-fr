---
title: "Initialisation de cha&#238;nes | Microsoft Docs"
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
  - "tableaux de caractères, initialiser"
  - "initialiser des tableaux, chaînes"
  - "chaînes (C++), initialiser"
ms.assetid: 0ab8079d-d0d3-48f9-afd1-36a7bb439b29
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Initialisation de cha&#238;nes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez initialiser un tableau de caractères \(ou des caractères larges\) avec un littéral de chaîne \(ou un littéral de chaîne étendu\).  Par exemple :  
  
```  
char code[ ] = "abc";  
```  
  
 initialise `code` en tant que tableau de caractères à quatre éléments.  Le quatrième élément est le caractère Null, qui termine tous les littéraux de chaîne.  
  
 Une liste d'identificateurs ne peut pas dépasser le nombre d'identificateurs à initialiser.  Si vous spécifiez une taille de tableau inférieure à celle de la chaîne, les caractères supplémentaires sont ignorés.  Par exemple, la déclaration suivante initialise `code` en tant que tableau de caractères à trois éléments :  
  
```  
char code[3] = "abcd";  
```  
  
 Seuls les trois premiers caractères de l'initialiseur sont assignés à `code`.  Le caractère `d` et le caractère Null de terminaison de la chaîne sont ignorés.  Notez que cela crée une chaîne non terminée \(autrement dit, une chaîne sans valeur 0 pour marquer sa terminaison\) et génère un message de diagnostic indiquant cette condition.  
  
 La déclaration  
  
```  
char s[] = "abc", t[3] = "abc";  
```  
  
 est identique à  
  
```  
char s[]  = {'a', 'b', 'c', '\0'},   
     t[3] = {'a', 'b', 'c' };  
```  
  
 Si la chaîne est plus courte que la taille de tableau spécifiée, les éléments restants du tableau sont initialisés à 0.  
  
 **Section spécifique à Microsoft**  
  
 Dans Microsoft C, les littéraux de chaîne peuvent contenir jusqu'à 2048 octets au total.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Initialisation](../c-language/initialization.md)