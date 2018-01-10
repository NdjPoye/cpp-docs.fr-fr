---
title: "Déplacer l’emplacement de définition | Documents Microsoft"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c6d507ac-c61e-4da2-95c8-d504b42e2520
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 838f3d01f5e6d8612948304b80b79cf9c7cb4720
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="move-definition-location"></a>Déplacer l'emplacement de définition
**Ce que :** vous permet de déplacer immédiatement une définition de fonction pour le fichier d’en-tête correspondant.

**Quand :** vous avez une fonction que vous souhaitez déplacer vers un fichier d’en-tête.  

**Pourquoi :** vous pouvez déplacer manuellement la fonction, mais cette fonctionnalité sera déplacer automatiquement, créez le fichier d’en-tête si nécessaire.

**Comment faire :**

1. Placez votre curseur de texte ou de la souris sur la fonction pour laquelle vous souhaitez déplacer.

   ![Code en surbrillance](images/movedefinition_highlight.png)

1. Ensuite, effectuez l’une des opérations suivantes :
   * **Clavier**
     * Appuyez sur **Ctrl +.** pour déclencher le **Actions rapides et refactorisations** menu et sélectionnez **déplacer la position de définition** dans le menu contextuel.
   * **Souris**
     * Avec le bouton droit et sélectionnez le **Actions rapides et refactorisations** menu et sélectionnez **déplacer la position de définition** dans le menu contextuel.

1. La fonction sera déplacée vers le fichier d’en-tête correspondant, qui s’affiche dans une fenêtre d’aperçu contextuelle.  Si le fichier d’en-tête n’existe pas, il sera également être créé et placé dans le projet.

   ![Création de déclaration / définition](images/movedefinition_result.png)
