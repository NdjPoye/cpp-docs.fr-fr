---
title: Création de déclaration / définition | Documents Microsoft
ms.custom: ''
ms.date: 11/16/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: 6b1cdcb2-765e-4b93-8cef-92b861f64eba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 60d583ec47a3f9c5b61599a5945e3cfa0d375b1d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="create-declaration--definition"></a>Créer la déclaration/la définition
**Ce que :** vous permet de générer immédiatement de la déclaration ou définition d’une fonction.

**Quand :** vous avez une fonction qui doit être un existe, ou vice versa.  

**Pourquoi :** vous pouvez créer manuellement la définition/déclaration, mais cela créera automatiquement, créez le fichier d’en-tête/le code si nécessaire.

**Comment :**

1. Placez votre curseur de texte ou de la souris sur la fonction pour laquelle vous souhaitez créer la déclaration ou la définition.

   ![Code mis en surbrillance](images/createdefinition_highlight.png)

1. Effectuez ensuite l'une des opérations suivantes :
   * **Clavier**
     * Appuyez sur **Ctrl+.** pour déclencher le **Actions rapides et refactorisations** menu et sélectionnez **créer de déclaration / définition** dans le menu contextuel.
   * **Souris**
     * Avec le bouton droit et sélectionnez le **Actions rapides et refactorisations** menu et sélectionnez **créer de déclaration / définition** dans le menu contextuel.

1. La définition/déclaration de la fonction sera créée dans le fichier source ou l’en-tête, qui s’affiche dans une fenêtre d’aperçu contextuelle.  Si le fichier source ou l’en-tête n’existe pas, il sera également être créé et placé dans le projet.

   ![Création de déclaration / définition](images/createdefinition_result.png)
