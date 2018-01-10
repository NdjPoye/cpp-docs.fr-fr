---
title: Modifier la Signature | Documents Microsoft
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8daaa060-7305-4035-99d2-8b460b4f4454
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5280b4940c2a52fc6e72b397300040ca4c1ac92e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="change-signature"></a>Changer la signature
**Ce que :** vous permet de modifier les paramètres d’une fonction.

**Quand :** vous souhaitez réorganiser, ajouter, supprimer ou modifier les paramètres d’une fonction qui est actuellement utilisé dans différents emplacements.  

**Pourquoi :** vous pourriez manuellement ces paramètres vous-même, puis rechercher tous les appels à cette fonction et les modifier une par une, mais qui peut entraîner des erreurs.  Cet outil refactorisation effectuera automatiquement la tâche.

**Comment faire :**

1. Placez le curseur de texte ou de la souris dans le nom de la méthode permettant de modifier ou de l’un de ses utilisations :

   ![Code en surbrillance](images/changesignature_highlight.png)

1. Ensuite, effectuez l’une des opérations suivantes :
   * **Clavier**
     * Appuyez sur **Ctrl + R**, puis **Ctrl + O**.  (Notez que le raccourci clavier peut varier en fonction du profil que vous avez sélectionné.)
     * Appuyez sur **Ctrl +.** pour déclencher le **Actions rapides et refactorisations** menu et sélectionnez **changement de Signature** dans le menu contextuel.
   * **Souris**
     * Sélectionnez **Modifier > refactoriser > Réorganiser les paramètres**.
     * Cliquez sur le code, sélectionnez le **Actions rapides et refactorisations** menu et sélectionnez **changement de Signature** dans le menu contextuel.

1. Dans le **modifier la Signature** boîte de dialogue qui s’affiche, vous pouvez utiliser les boutons sur le côté droit pour modifier la signature de méthode :

   ![Modifiez la boîte de dialogue Signature](images/changesignature_dialog.png)

   | Bouton | Description
   | ------ | ---
   | **Haut/bas**    | Déplacer le paramètre sélectionné en haut et bas de la liste
   | **Ajouter**        | Ajouter un nouveau paramètre à la liste
   | **Supprimer**     | Supprimez le paramètre sélectionné dans la liste
   | **Modifier**     | Modifier le paramètre sélectionné en modifiant son type, nom et s’il est facultatif et sa valeur injecté serait
   | **Rétablir**     | Restaurer le paramètre sélectionné de son état d’origine
   | **Rétablissez toutes les** | Restaurer tous les paramètres de l’état d’origine

   > [!TIP]
   > Utilisez le **des modifications des références de version préliminaire ignorer si toutes les références sont confirmées** case à cocher pour apporter les modifications immédiatement sans la fenêtre d’aperçu dépilé en premier.

   Lorsque vous ajoutez ou modifier un paramètre, vous verrez la **ajouter un paramètre** ou **modifier le paramètre** fenêtre.

   ![Ajouter/modifier un paramètre](images/changesignature_addmodify.png)

   Ici, vous pouvez procédez comme suit :

   | Entrée | Description
   | ----- | ---
   | **Type**               | Le type du paramètre (int, double, float, etc..)
   | **Name**               | Le nom du paramètre
   | **Paramètre facultatif** | Rend le paramètre éventuellement spécifié
   | **Valeur injecté**     | La valeur insérée dans tous les appels à la fonction dans laquelle le paramètre n’est pas spécifié (valide uniquement pour **ajouter**)
   | **Valeur par défaut**      | La valeur utilisée par la fonction si l’appelant ne spécifie pas une (valide uniquement pour **paramètres facultatifs**)

1. Utilisez le **étendue de recherche** liste déroulante pour sélectionner si les modifications seront appliquées pour le projet ou la solution entière.

1. Lorsque vous avez terminé, appuyez sur la **OK** bouton apporter les modifications.  Assurez-vous que les modifications que vous avez demandée sont s’effectuées correctement.  Pour activer ou désactiver le changement de nom d’un élément, utilisez les cases à cocher dans la moitié supérieure de la fenêtre.

   ![Aperçu de la Signature des modifications](images/changesignature_preview.png)

1. Lorsque tout semble correct, cliquez sur le **appliquer** bouton et la fonction seront modifiées dans votre code source.

   ![Modifier le résultat de la Signature](images/changesignature_result.png)