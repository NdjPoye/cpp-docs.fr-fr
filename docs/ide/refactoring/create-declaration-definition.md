---
title: "Création de déclaration / définition | Documents Microsoft"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6b1cdcb2-765e-4b93-8cef-92b861f64eba
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 889c8acf5e0ef0ed6a7ac90088a6188658d49d75
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="create-declaration--definition"></a>Créer la déclaration/la définition
**Ce que :** vous permet de générer immédiatement de la déclaration ou définition d’une fonction.

**Quand :** vous avez une fonction qui doit être un existe, ou vice versa.  

**Pourquoi :** vous pouvez créer manuellement la définition/déclaration, mais cela créera automatiquement, créez le fichier d’en-tête/le code si nécessaire.

**Comment faire :**

1. Placez votre curseur de texte ou de la souris sur la fonction pour laquelle vous souhaitez créer la déclaration ou la définition.

   ![Code en surbrillance](images/createdefinition_highlight.png)

1. Ensuite, effectuez l’une des opérations suivantes :
   * **Clavier**
     * Appuyez sur **Ctrl +.** pour déclencher le **Actions rapides et refactorisations** menu et sélectionnez **créer de déclaration / définition** dans le menu contextuel.
   * **Souris**
     * Avec le bouton droit et sélectionnez le **Actions rapides et refactorisations** menu et sélectionnez **créer de déclaration / définition** dans le menu contextuel.

1. La définition/déclaration de la fonction sera créée dans le fichier source ou l’en-tête, qui s’affiche dans une fenêtre d’aperçu contextuelle.  Si le fichier source ou l’en-tête n’existe pas, il sera également être créé et placé dans le projet.

   ![Création de déclaration / définition](images/createdefinition_result.png)
