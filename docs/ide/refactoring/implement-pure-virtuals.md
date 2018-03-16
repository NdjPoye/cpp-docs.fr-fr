---
title: "Implémenter les virtuels purs | Documents Microsoft"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea9b4719-34a3-474a-b4ec-05b1859f80f1
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f311c2e5832754bfd785084b9aa930b5dbe43845
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2018
---
# <a name="implement-pure-virtuals"></a>Implémenter les virtuels purs
**Ce que :** vous permet de générer d’immédiatement le code requis pour implémenter toutes les méthodes virtuelles pures dans une classe. 

**Quand :** vous voulez hériter d’une classe avec des fonctions virtuelles pures.  

**Pourquoi :** vous pouvez implémenter manuellement les fonctions virtuelles pures tous les un par un, mais cette fonctionnalité génère automatiquement toutes les signatures de méthode.

**Comment :**

1. Placez votre curseur de texte ou de la souris sur la classe dans laquelle vous souhaitez implémenter les fonctions virtuelles pures de la classe de base.

   ![Code mis en surbrillance](images/virtuals_highlight.png)

1. Effectuez ensuite l'une des opérations suivantes :
   * **Clavier**
     * Appuyez sur **Ctrl+.** pour déclencher le **Actions rapides et refactorisations** menu et sélectionnez **implémenter tous les virtuels purs pour la classe*ClassName*'** dans le menu contextuel, où  *ClassName* est le nom de la classe sélectionnée.
   * **Souris**
     * Avec le bouton droit et sélectionnez le **Actions rapides et refactorisations** menu et sélectionnez **implémenter tous les virtuels purs pour la classe*ClassName*'** dans le menu contextuel, où  *ClassName* est le nom de la classe sélectionnée.

1. Les signatures de méthode virtuelle pure seront créés automatiquement, prêt à être implémentée.

   ![Implémenter les virtuels purs résultat](images/virtuals_result.png)
