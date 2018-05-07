---
title: Implémenter les virtuels purs | Documents Microsoft
ms.custom: ''
ms.date: 11/16/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: ea9b4719-34a3-474a-b4ec-05b1859f80f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: afce516f2718a76658846ed4f992aeabff75330b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
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
