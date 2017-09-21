---
title: "Opérateurs de bits C | Microsoft Docs"
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
- '| operator, bitwise operators'
- bitwise operators, Visual C
- bitwise operators
- operators [C], bitwise
- ^ operator, bitwise operators
- AND operator
- ampersand operator (&)
- ^ operator
- '& operator, bitwise operators'
ms.assetid: e22127b1-9a2d-4876-b01d-c8f72cec3317
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 620177616e8b60d910d064d7c345633ac5155020
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="c-bitwise-operators"></a>Opérateurs de bits C
Les opérateurs au niveau du bit effectuent de bits AND (**&**), des opérations de bits OR exclusives (**^**) et opérations de bits OR inclusives (**&#124;**).  
  
 **Syntaxe**  
  
 *AND-expression* :  
 *equality-expression*  
  
 *AND-expression*  **&**  *equality-expression*  
  
 *exclusive-OR-expression* :  
 *AND-expression*  
  
 *exclusive-OR-expression*  **^**  *AND-expression*  
  
 *inclusive-OR-expression* :  
 *exclusive-OR-expression*  
  
 *inclusive-OR-expression* &#124; *exclusive-OR-expression*  
  
 Les opérandes des opérateurs de bits doivent avoir des types intégraux, mais leurs types peuvent être différents. Ces opérateurs exécutent les conversions arithmétiques habituelles ; le type du résultat est le type de l'opérande après conversion.  
  
 Les opérateurs de bits C sont décrits ci-dessous :  
  
|Opérateur|Description|  
|--------------|-----------------|  
|**&**|L'opérateur de bits AND compare chaque bit de son premier opérande au bit correspondant de son second opérande. Si les deux bits sont 1, le bit de résultat correspondant a la valeur 1. Sinon, le bit de résultat correspondant a la valeur 0.|  
|**^**|L’opérateur de bits OR exclusif compare chaque bit de son premier opérande au bit correspondant de son second opérande. Si un bit est 0 et que l'autre bit est 1, le bit de résultat correspondant prend la valeur 1. Sinon, le bit de résultat correspondant a la valeur 0.|  
|**&#124;**|L’opérateur de bits OR exclusif compare chaque bit de son premier opérande au bit correspondant de son second opérande. Si l'un des bits est 1, le bit correspondant de résultat a la valeur 1. Sinon, le bit de résultat correspondant a la valeur 0.|  
  
## <a name="examples"></a>Exemples  
 Ces déclarations sont utilisées pour les trois exemples suivants :  
  
```  
short i = 0xAB00;  
short j = 0xABCD;  
short n;  
  
n = i & j;  
```  
  
 Le résultat affecté à `n` dans ce premier exemple est le même que `i` (0xAB00 hexadécimal).  
  
```  
n = i | j;  
  
n = i ^ j;  
```  
  
 L’OR inclusif au niveau du bit dans le deuxième exemple entraîne la valeur 0xABCD (hexadécimale), tandis que l’opération OR exclusive au niveau du bit dans le troisième exemple produit 0xCD (hexadécimal).  
  
 **Section spécifique à Microsoft**  
  
 Les résultats d’une opération au niveau du bit sur des entiers signés sont définis par l’implémentation en fonction de la norme ANSI C. Pour le compilateur Microsoft C, les opérations au niveau du bit sur les entiers signés fonctionnent de la même façon que les opérations au niveau du bit sur les entiers non signés. Par exemple, les valeurs `-16 & 99` peuvent être exprimées au format binaire sous la forme  
  
```  
  11111111 11110000  
& 00000000 01100011  
  _________________  
  00000000 01100000  
```  
  
 Le résultat de l'opération de bits AND est 96 décimal.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Opérateur de bits AND : &](../cpp/bitwise-and-operator-amp.md)   
 [Opérateur de bits OR exclusif : ^](../cpp/bitwise-exclusive-or-operator-hat.md)   
 [Opérateur de bits OR inclusif : &#124;](../cpp/bitwise-inclusive-or-operator-pipe.md)