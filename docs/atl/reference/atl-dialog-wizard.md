---
title: Assistant dialogue ATL | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vc.codewiz.class.atl.dlg.overview
dev_langs: C++
helpviewer_keywords:
- ATL projects, adding dialog resources
- ATL Dialog Wizard
ms.assetid: b0b9ace5-83c9-40d3-82c3-eb6293f10583
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 003cda9f3b0916cb7c86dfce874840268a64dbff
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="atl-dialog-wizard"></a>Assistant Boîte de dialogue ATL
Cet Assistant insère dans le projet un objet boîte de dialogue ATL, dérivé de [CAxDialogImpl](../../atl/reference/caxdialogimpl-class.md). Une boîte de dialogue dérivé `CAxDialogImpl` peut héberger des contrôles ActiveX.  
  
 L’Assistant crée une ressource de boîte de dialogue avec la valeur par défaut **OK** et **Annuler** boutons. Vous pouvez modifier la ressource de boîte de dialogue et ajouter des contrôles ActiveX à l’aide de la [boîte de dialogue Éditeur](../../windows/dialog-editor.md) dans l’affichage des ressources.  
  
 L’Assistant insère dans le fichier d’en-tête une [table des messages](../../atl/message-maps-atl.md) et déclarations pour la valeur par défaut de la gestion des événements click. Consultez [mise en œuvre d’une boîte de dialogue](../../atl/implementing-a-dialog-box.md) pour plus d’informations sur les boîtes de dialogue ATL.  
  
 **Nom court**  
 Définit le nom abrégé de l’objet de la boîte de dialogue ATL. Le nom que vous fournissez détermine le nom de classe et le fichier (.cpp et .h), sauf si vous modifiez ces champs individuellement.  
  
 `Class`  
 Définit le nom de la classe à créer. Ce nom est basé sur le nom que vous fournissez dans **nom court**, précédé de « C » (préfixe classique pour un nom de classe.  
  
 **fichier .h**  
 Définit le nom du fichier d’en-tête pour la nouvelle classe d’objet. Par défaut, ce nom est basé sur le nom que vous fournissez dans **nom court**. Cliquez sur le bouton de sélection pour enregistrer le nom de fichier à l’emplacement de votre choix ou pour ajouter la déclaration de classe à un fichier existant. Si vous choisissez un fichier existant, l’Assistant enregistrera pas à l’emplacement sélectionné jusqu'à ce que vous cliquez sur **Terminer** dans l’Assistant.  
  
 L’Assistant ne remplacera pas un fichier. Si vous sélectionnez le nom d’un fichier existant, lorsque vous cliquez sur **Terminer**, l’Assistant vous invite à indiquer si la déclaration de classe doit être ajoutée au contenu du fichier. Cliquez sur **Oui** pour ajouter le fichier ; cliquez sur **non** pour revenir à l’Assistant et spécifiez un autre nom de fichier.  
  
 **fichier .cpp**  
 Définit le nom du fichier d’implémentation pour la nouvelle classe d’objet. Par défaut, ce nom est basé sur le nom que vous fournissez dans **nom court**. Cliquez sur le bouton de sélection pour enregistrer le nom de fichier à l’emplacement de votre choix. Le fichier n’est pas enregistré à l’emplacement sélectionné jusqu'à ce que vous cliquez sur **Terminer** dans l’Assistant.  
  
 L’Assistant ne remplacera pas un fichier. Si vous sélectionnez le nom d’un fichier existant, lorsque vous cliquez sur **Terminer**, l’Assistant vous invite à indiquer si l’implémentation de classe doit être ajoutée au contenu du fichier. Cliquez sur **Oui** pour ajouter le fichier ; cliquez sur **non** pour revenir à l’Assistant et spécifiez un autre nom de fichier.  
  
## <a name="see-also"></a>Voir aussi  
 [Boîte de dialogue ATL](../../atl/reference/adding-an-atl-dialog-box.md)

