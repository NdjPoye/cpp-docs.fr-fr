---
title: "Convertir en littéral de chaîne brute | Documents Microsoft"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fffbfee4-66ee-42ba-aeb9-df07fb702c51
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c237f9042707654c913a24db916a82971603bb0a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="convert-to-raw-string-literal"></a>Convertir en littéral de chaîne brut
**Ce que :** vous permet de transformer une chaîne en une chaîne brute C++ littéral.

**Quand :** vous avez une chaîne avec des caractères d’échappement qui ne doivent pas être traités comme des caractères d’échappement.

**Pourquoi :** Impossible de double échappement caractères, mais cela a pour conséquence des chaînes à confusion et illisibles.  À l’aide de littéraux de chaîne bruts rend beaucoup plus facile à lire des chaînes.

**Comment faire :**

1. Placez le curseur de texte ou de la souris au-dessus de la chaîne d’échappement à convertir.

   ![Code en surbrillance](images/stringliteral_highlight.png)

1. Ensuite, effectuez l’une des opérations suivantes :
   * **Clavier**
     * Appuyez sur **Ctrl +.** pour déclencher le **Actions rapides et refactorisations** menu et sélectionnez **convertir en littéral de chaîne brute** dans le menu contextuel.
   * **Souris**
     * Cliquez sur le code, sélectionnez le **Actions rapides et refactorisations** menu et sélectionnez **convertir en littéral de chaîne brute** dans le menu contextuel.
     * Cliquez sur le ![Lightbulb](images/bulb.png) icône qui apparaît dans la marge de gauche et sélectionnez **convertir en littéral de chaîne brute** dans le menu contextuel.

1. La chaîne doit être convertie immédiatement dans un littéral de chaîne brute.  

   ![Résultat littéral de chaîne brute](images/stringliteral_result.png)