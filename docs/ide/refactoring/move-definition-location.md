---
title: Déplacer l’emplacement de définition | Documents Microsoft
ms.custom: ''
ms.date: 11/16/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: c6d507ac-c61e-4da2-95c8-d504b42e2520
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 44211105429e33c136999a7877ac6ee42af29f17
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="move-definition-location"></a>Déplacer l'emplacement de définition
**Ce que :** vous permet de déplacer immédiatement une définition de fonction pour le fichier d’en-tête correspondant.

**Quand :** vous avez une fonction que vous souhaitez déplacer vers un fichier d’en-tête.  

**Pourquoi :** vous pouvez déplacer manuellement la fonction, mais cette fonctionnalité sera déplacer automatiquement, créez le fichier d’en-tête si nécessaire.

**Comment :**

1. Placez votre curseur de texte ou de la souris sur la fonction pour laquelle vous souhaitez déplacer.

   ![Code mis en surbrillance](images/movedefinition_highlight.png)

1. Effectuez ensuite l'une des opérations suivantes :
   * **Clavier**
     * Appuyez sur **Ctrl+.** pour déclencher le **Actions rapides et refactorisations** menu et sélectionnez **déplacer la position de définition** dans le menu contextuel.
   * **Souris**
     * Avec le bouton droit et sélectionnez le **Actions rapides et refactorisations** menu et sélectionnez **déplacer la position de définition** dans le menu contextuel.

1. La fonction sera déplacée vers le fichier d’en-tête correspondant, qui s’affiche dans une fenêtre d’aperçu contextuelle.  Si le fichier d’en-tête n’existe pas, il sera également être créé et placé dans le projet.

   ![Création de déclaration / définition](images/movedefinition_result.png)
