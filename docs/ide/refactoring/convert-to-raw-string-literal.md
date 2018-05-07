---
title: Convertir en littéral de chaîne brute | Documents Microsoft
ms.custom: ''
ms.date: 11/16/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: fffbfee4-66ee-42ba-aeb9-df07fb702c51
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b98825719e7b3c0d8eb760a2ec50644b5eddd54e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="convert-to-raw-string-literal"></a>Convertir en littéral de chaîne brut
**Ce que :** vous permet de transformer une chaîne en une chaîne brute C++ littéral.

**Quand :** vous avez une chaîne avec des caractères d’échappement qui ne doivent pas être traités comme des caractères d’échappement.

**Pourquoi :** Impossible de double échappement caractères, mais cela a pour conséquence des chaînes à confusion et illisibles.  À l’aide de littéraux de chaîne bruts rend beaucoup plus facile à lire des chaînes.

**Comment :**

1. Placez le curseur de texte ou de la souris au-dessus de la chaîne d’échappement à convertir.

   ![Code mis en surbrillance](images/stringliteral_highlight.png)

1. Effectuez ensuite l'une des opérations suivantes :
   * **Clavier**
     * Appuyez sur **Ctrl+.** pour déclencher le **Actions rapides et refactorisations** menu et sélectionnez **convertir en littéral de chaîne brute** dans le menu contextuel.
   * **Souris**
     * Cliquez sur le code, sélectionnez le **Actions rapides et refactorisations** menu et sélectionnez **convertir en littéral de chaîne brute** dans le menu contextuel.
     * Cliquez sur le ![Lightbulb](images/bulb.png) icône qui apparaît dans la marge de gauche et sélectionnez **convertir en littéral de chaîne brute** dans le menu contextuel.

1. La chaîne doit être convertie immédiatement dans un littéral de chaîne brute.  

   ![Résultat littéral de chaîne brute](images/stringliteral_result.png)