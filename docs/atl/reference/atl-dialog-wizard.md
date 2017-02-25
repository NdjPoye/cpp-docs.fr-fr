---
title: "Dialogue ATL (Assistant) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.dlg.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Dialogue ATL (Assistant)"
  - "Projets ATL, ajouter des ressources de boîtes de dialogue"
ms.assetid: b0b9ace5-83c9-40d3-82c3-eb6293f10583
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Dialogue ATL (Assistant)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cet Assistant insère dans le projet un objet boîte de dialogue ATL, dérivé de [CAxDialogImpl](../../atl/reference/caxdialogimpl-class.md).  Une boîte de dialogue dérivée de `CAxDialogImpl` peut héberger des contrôles ActiveX.  
  
 L'Assistant créé une ressource de boîte de dialogue avec des boutons **OK** et **Annuler** par défaut.  Vous pouvez éditer la ressource de boîte de dialogue et ajouter des contrôles ActiveX en utilisant l'[Éditeur de boîtes de dialogue](../../mfc/dialog-editor.md) en mode Affichage des ressources.  
  
 L'Assistant insère dans le fichier d'en\-tête une [table des messages](../../atl/message-maps-atl.md) et des déclarations pour gérer les événements Click par défaut.  Consultez [Implémentation d'une boîte de dialogue](../../atl/implementing-a-dialog-box.md) pour plus d'informations sur les boîtes de dialogue ATL.  
  
 **Nom court**  
 Définit le nom abrégé de l'objet de dialogue ATL.  Le nom que vous indiquez détermine le nom de la classe et du fichier \(.cpp et .h\), à moins que vous ne modifiiez ces champs individuellement.  
  
 `Class`  
 Définit le nom de la classe que vous souhaitez créer.  Ce nom est fondé sur le nom que vous entrez dans la zone **Nom court**, précédé de « C » \(préfixe classique pour un nom de classe\).  
  
 **fichier .h**  
 Définit le nom du fichier d'en\-tête de la nouvelle classe d'objets.  Par défaut, ce nom est fondé sur le nom que vous entrez dans la zone **Nom court**.  Cliquez sur le bouton de sélection pour enregistrer le nom de fichier à l'emplacement de votre choix ou pour ajouter la déclaration de classe à un fichier existant.  Si vous sélectionnez un fichier existant, l'Assistant ne l'enregistrera pas à l'emplacement choisi tant que vous n'aurez pas cliqué sur **Terminer** dans l'Assistant.  
  
 L'Assistant n'écrase pas un fichier.  Si vous sélectionnez le nom d'un fichier existant et cliquez sur **Terminer**, l'Assistant vous demande d'indiquer si la déclaration de classe doit être ajoutée au contenu du fichier.  Cliquez sur **Oui** pour ajouter le fichier ; cliquez sur **Non** pour revenir à l'Assistant et spécifier un autre nom de fichier.  
  
 **fichier .cpp**  
 Définit le nom du fichier d'implémentation pour la nouvelle classe d'objet.  Par défaut, ce nom est fondé sur le nom que vous entrez dans la zone **Nom court**.  Cliquez sur le bouton de sélection pour enregistrer le nom de fichier à l'emplacement de votre choix.  Le fichier n'est pas enregistré à l'emplacement souhaité tant que vous n'avez pas cliqué sur **Terminer** dans l'Assistant.  
  
 L'Assistant n'écrase pas un fichier.  Si vous sélectionnez le nom d'un fichier existant et cliquez sur **Terminer**, l'Assistant vous invite à indiquer si l'implémentation de classe doit être ajoutée au contenu du fichier.  Cliquez sur **Oui** pour ajouter le fichier ; cliquez sur **Non** pour revenir à l'Assistant et spécifier un autre nom de fichier.  
  
## Voir aussi  
 [ATL Dialog Box](../../atl/reference/adding-an-atl-dialog-box.md)