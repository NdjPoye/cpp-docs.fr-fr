---
title: Extraire la fonction | Documents Microsoft
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e31d1249-9705-4511-acbd-9f6fe73bdf2d
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dbcd323292e301857c65d908047ab14948b86573
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2018
---
# <a name="extract-function"></a>Extract, fonction
**Ce que :** vous permet de transformer un fragment de code dans sa propre fonction.

**Quand :** vous avez un fragment de code existant dans une fonction qui doit être appelée à partir d’une autre fonction.  

**Pourquoi :** vous pouvez copier/coller ce code, mais cela entraîne une duplication.  Une meilleure solution consiste à refactoriser ce fragment dans sa propre fonction qui peut être appelée librement par toute autre fonction.

**Comment :**

1. Mettez en surbrillance le code à extraire :

   ![Code mis en surbrillance](images/extractfunction_highlight.png)

1. Effectuez ensuite l'une des opérations suivantes :
   * **Clavier**
     * Appuyez sur **Ctrl+R**, puis **Ctrl+M**.  (Notez que le raccourci clavier peut varier en fonction du profil que vous avez sélectionné.)
     * Appuyez sur **Ctrl+.** pour déclencher le **Actions rapides et refactorisations** menu et sélectionnez **fonction Extract (expérimental)** dans le menu contextuel.
   * **Souris**
     * Sélectionnez **Modifier > refactoriser > Extract, fonction (expérimentale)**.
     * Cliquez sur le code, sélectionnez le **Actions rapides et refactorisations** menu et sélectionnez **fonction Extract (expérimental)** dans le menu contextuel.
     * Cliquez sur le ![Lightbulb](images/bulb.png) icône qui apparaît dans la marge de gauche et sélectionnez **fonction Extract (expérimental)** dans le menu contextuel.

1. Dans le **extraire (expérimental) la fonction/méthode** fenêtre, entrez le nouveau nom de fonction, sélectionnez où vous souhaitez que le code doit être placé, puis cliquez sur le **OK** bouton.  

   ![Extract (fonction) (fonction)](images/extractfunction_dialog.png)

1. La nouvelle fonction sera créée lorsque vous avez spécifié un prototype de fonction dans le fichier d’en-tête correspondant, et le code d’origine sera modifié pour appeler cette fonction.

   ![Extraire le résultat de fonction](images/extractfunction_result.png)