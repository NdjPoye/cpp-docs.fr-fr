---
title: "Initialisation de chaînes | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- character arrays, initializing
- strings [C++], initializing
- initializing arrays, strings
ms.assetid: 0ab8079d-d0d3-48f9-afd1-36a7bb439b29
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 830e959e8cd9e57745d08da3d4184fbe11a5bb6a
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="initializing-strings"></a>Initialisation de chaînes
Vous pouvez initialiser un tableau de caractères (ou des caractères larges) avec un littéral de chaîne (ou un littéral de chaîne étendu). Exemple :  
  
```  
char code[ ] = "abc";  
```  
  
 initialise `code` en tant que tableau de caractères à quatre éléments. Le quatrième élément est le caractère Null, qui termine tous les littéraux de chaîne.  
  
 Une liste d'identificateurs ne peut pas dépasser le nombre d'identificateurs à initialiser. Si vous spécifiez une taille de tableau inférieure à celle de la chaîne, les caractères supplémentaires sont ignorés. Par exemple, la déclaration suivante initialise `code` en tant que tableau de caractères à trois éléments :  
  
```  
char code[3] = "abcd";  
```  
  
 Seuls les trois premiers caractères de l'initialiseur sont assignés à `code`. Le caractère `d` et le caractère Null de terminaison de la chaîne sont ignorés. Notez que cela crée une chaîne non terminée (autrement dit, une chaîne sans valeur 0 pour marquer sa terminaison) et génère un message de diagnostic indiquant cette condition.  
  
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
  
## <a name="see-also"></a>Voir aussi  
 [Initialisation](../c-language/initialization.md)
