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
ms.workload: cplusplus
ms.openlocfilehash: 12aa512270ecce4564561634f99be9cbf155448a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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