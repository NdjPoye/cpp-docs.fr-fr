---
title: "Surcharge de l’opérateur &gt;&gt; pour vos propres classes | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- operator>>
- operator>>, overloading for your own classes
- operator >>, overloading for your own classes
ms.assetid: 40dab4e0-3f97-4745-9cc8-b86e740fa246
caps.latest.revision: 8
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 4ac48927cc0b68dc958a09ee541c41895f11f86b
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="overloading-the-gtgt-operator-for-your-own-classes"></a>Surcharge de l’opérateur &gt;&gt; pour vos propres classes
Les flux d’entrée utilisent l’opérateur d’extraction (`>>`) pour les types standards. Vous pouvez écrire des opérateurs d’extraction similaires pour vos propres types, en veillant à utiliser les espaces blancs de façon appropriée.  
  
 Voici un exemple d’opérateur d’extraction pour la classe `Date` présentée précédemment :  
  
```  
istream& operator>> (istream& is, Date& dt)  
{  
    is>> dt.mo>> dt.da>> dt.yr;  
    return is;  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Flux d’entrée](../standard-library/input-streams.md)


