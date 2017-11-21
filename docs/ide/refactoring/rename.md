---
title: Renommer | Documents Microsoft
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 64b42a88-3bd9-4399-8b96-75bceffc353b
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d8e4152a1c920a243be9d4aa23712420893e29f5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="rename"></a>Renommer
**Ce que :** vous permet de renommer les identificateurs pour les symboles de code, tels que les champs, les variables locales, les méthodes, les espaces de noms, les propriétés et les types.

**Quand :** à quelque chose renommer en toute sécurité sans avoir à rechercher toutes les instances et copier/coller le nouveau nom.  

**Pourquoi :** en copiant et collant le nouveau nom dans un projet entier probablement entraîner des erreurs.  Cet outil refactorisation précisément effectue l’action de changement de nom.

**Comment faire :**

1. Mettez en surbrillance ou placez le curseur de texte à l’intérieur de l’élément à renommer :

   ![Code en surbrillance](images/rename_highlight.png)

1. Ensuite, effectuez l’une des opérations suivantes :
   * **Clavier**
     * Appuyez sur **Ctrl + R**, puis **Ctrl + R**.  (Notez que le raccourci clavier peut varier en fonction du profil que vous avez sélectionné.)
   * **Souris**
     * Sélectionnez **Modifier > refactoriser > Renommer**.
     * Le code d’avec le bouton droit et sélectionnez **renommer**.

1. Dans le **renommer** fenêtre qui s’affiche, entrez le nouveau nom pour l’élément sélectionné et cliquez sur le **aperçu** bouton.  Modifier la **étendue de recherche** si vous avez besoin élargir ou restreindre l’étendue de la modification du nom.

   ![boîte de dialogue Renommer](images/rename_dialog.png)

   > [!TIP]
   > Vous pouvez ignorer l’aperçu en vérifiant la **aperçu d’ignorer des modifications si les références sont confirmées** option.

1. Lorsque le **afficher les modifications - Renommer** fenêtre s’affiche, vérifiez que les modifications que vous avez demandée sont s’effectuées correctement.  Pour activer ou désactiver le changement de nom d’un élément, utilisez les cases à cocher dans la moitié supérieure de la fenêtre.

   ![Renommer l’aperçu](images/rename_preview.png)

1. Lorsque tout semble correct, cliquez sur le **appliquer** bouton et l’élément seront renommées dans votre code source.
