---
title: "Bo&#238;tes de dialogue dans OLE | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "boîtes de dialogue"
  - "boîtes de dialogue, à propos des boîtes de dialogue"
  - "boîtes de dialogue, OLE"
  - "Insérer un objet"
  - "boîtes de dialogue MFC, boîtes de dialogue OLE"
  - "boîtes de dialogue OLE"
  - "boîtes de dialogue OLE, à propos des boîtes de dialogue OLE"
ms.assetid: 73c41eb8-738a-4d02-9212-d3395bb09a3a
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Bo&#238;tes de dialogue dans OLE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsqu'un utilisateur exécute une application OLE\-compatible, il arrive que l'application ait besoin d'informations de la part de l'utilisateur pour effectuer l'opération.  Les classes OLE MFC fournissent plusieurs boîtes de dialogue pour recueillir les informations nécessaires.  Cette rubrique répertorie les tâches gérées par les boîtes de dialogue OLE et les classes nécessaires pour afficher ces boîtes de dialogue.  Pour plus d'informations sur les boîtes de dialogue OLE et les structures utilisées pour personnaliser leur comportement, consultez [Guide de MFC](../mfc/mfc-desktop-applications.md).  
  
 *Insérer un objet*  
 Cette boîte de dialogue permet à l'utilisateur d'insérer des objets nouvellement créés ou existants dans le document composite.  Elle permet également à l'utilisateur de choisir d'afficher l'élément comme icône et active le bouton de commande de l'icône de modification.  Afficher cette boîte de dialogue lorsque l'utilisateur sélectionne l'objet d'insertion dans le menu Edition.  Utilisez la classe [COleInsertDialog](../mfc/reference/coleinsertdialog-class.md) pour afficher cette boîte de dialogue.  Notez que vous ne pouvez pas insérer une application MDI en elle\-même.  Une application qui est un conteneur\/serveur ne peut pas être insérée dans elle\-même à moins qu'elle soit une application de SDI.  
  
 *Collage spécial...*  
 Cette boîte de dialogue permet à l'utilisateur de contrôler le format utilisé en collant des données dans un document composite.  L'utilisateur peut choisir le format des données, d'inclure ou lier les données, et si l'afficher sous forme de icône ou non.  Afficher cette boîte de dialogue lorsque l'utilisateur sélectionne Collage Spécial dans le menu Edition.  Utilisez la classe [COlePasteSpecialDialog](../mfc/reference/colepastespecialdialog-class.md) pour afficher cette boîte de dialogue.  
  
 *Modification d'icône*  
 Cette boîte de dialogue permet à l'utilisateur de choisir quelle icône s'affiche pour représenter l'élément lié ou incorporé.  Affichez cette boîte de dialogue lorsque l'utilisateur sélectionne l'icône de modification du menu Edition ou choisit le bouton de l'icône de modification dans le collage spécial ou les boîtes de dialogue de conversion.  Affichez le également lorsque l'utilisateur ouvre la boîte de dialogue d'insertion et choisit l'affichage comme icône.  Utilisez la classe [COleChangeIconDialog](../mfc/reference/colechangeicondialog-class.md) pour afficher cette boîte de dialogue.  
  
 *Convertir*  
 Cette boîte de dialogue permet à l'utilisateur de modifier le type d'un document ou d'un élément lié.  Par exemple, si vous avez incorporé un métafichier dans un document composite et voulez ensuite utiliser une autre application pour modifier un métafichier autonome, utilisez la boîte de dialogue de conversion.  Cette boîte de dialogue est généralement affichée en cliquant sur l'objet *type d'élément* dans le menu Edition, puis dans le menu en cascade, cliquez sur conversion.  Utilisez la classe [COleConvertDialog](../mfc/reference/coleconvertdialog-class.md) pour afficher cette boîte de dialogue.  Pour obtenir un exemple, exécutez l'exemple de liaison et incorporation d'objets MFC [OCLIENT](../top/visual-cpp-samples.md).  
  
 *modifier ou mettre à jour des liens*  
 La boîte de dialogue modification de liens permet à l'utilisateur de modifier des informations sur la source de l'objet lié.  La boîte de dialogue de mise à jour de liens vérifie les sources de tous les éléments dans la boîte de dialogue actuelle et affiche la boîte de dialogue de modification de liens si nécessaire.  Affichez la boîte de dialogue de Liens des modifications lorsque l'utilisateur choisit Liens dans le menu Edition.  La boîte de dialogue de mise à jour de liens est généralement affichée lorsqu'un document composite s'ouvre.  Utilisez [COleLinksDialog](../mfc/reference/colelinksdialog-class.md) ou la classe [COleUpdateDialog](../mfc/reference/coleupdatedialog-class.md), selon quelle boîte de dialogue vous souhaitez afficher.  
  
 *Serveur occupé ou serveur ne répond pas*  
 La boîte de dialogue totale d'activité du serveur est affichée lors de la tentative d'utilisateur pour activer un élément et le serveur ne peut pas traiter la demande, généralement parce que le serveur est en cours de utilisation par un utilisateur ou une tâche différents.  La boîte de dialogue "serveur ne répond pas" est affichée si le serveur ne répond pas du tout à la demande d'activation.  Ces boîtes de dialogue apparaissent via `COleMessageFilter`, basées sur une implémentation de l'interface OLE **IMessageFilter**, et l'utilisateur peut choisir d'essayer l'activation les demandent de nouveau.  Utilisez la classe [COleBusyDialog](../mfc/reference/colebusydialog-class.md) pour afficher cette boîte de dialogue.  
  
## Voir aussi  
 [Boîtes de dialogue](../mfc/dialog-boxes.md)   
 [Cycle de vie d'une boîte de dialogue](../mfc/life-cycle-of-a-dialog-box.md)   
 [OLE](../mfc/ole-in-mfc.md)