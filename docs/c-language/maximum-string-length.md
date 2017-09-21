---
title: "Longueur de chaîne maximale | Microsoft Docs"
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
- lengths, strings
- string length, maximum
- maximum string length
- strings [C++], length
ms.assetid: 99a80e4a-6212-47b7-a6bd-bdf99bd44928
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
ms.openlocfilehash: 51b9944c1008409c00f3a4d32cfbaef63de0b4e6
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="maximum-string-length"></a>Longueur maximale de chaîne
**Section spécifique à Microsoft**  
  
 La compatibilité ANSI requiert un compilateur pour accepter jusqu'à 509 caractères dans un littéral de chaîne après concaténation. La longueur maximale d'un littéral de chaîne autorisé dans Microsoft C est d'environ 2 048 octets. Toutefois, si le littéral de chaîne comporte des parties placées entre guillemets, le préprocesseur concatène les parties dans une chaîne unique, et pour chaque ligne concaténée, il ajoute un octet supplémentaire au nombre total d'octets.  
  
 Par exemple, supposons qu'une chaîne se compose de 40 lignes avec 50 caractères par ligne (2 000 caractères), et une ligne avec 7 caractères, et que chaque ligne est placée entre guillemets doubles. Cela ajoute jusqu'à 2 007 octets plus un octet pour le caractère null de fin, pour un total de 2 008 octets. Sur la concaténation, un caractère supplémentaire est ajouté pour les 40 premières lignes. Cela donne un total de 2 048 octets. Notez, cependant, qui si les continuations de ligne (\\) sont utilisées au lieu des guillemets doubles, le préprocesseur n'ajoute pas de caractère supplémentaire pour chaque ligne.  
  
 Alors qu'une chaîne entre guillemets individuelle ne peut pas dépasser 2 048 octets, un littéral de chaîne d'environ 65 535 octets peut être construit en concaténant les chaînes.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Littéraux de chaîne C](../c-language/c-string-literals.md)