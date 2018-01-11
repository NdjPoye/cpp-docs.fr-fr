---
title: "Classes de boîte de dialogue communes OLE | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.ole
dev_langs: C++
helpviewer_keywords:
- ActiveX classes [MFC]
- dialog classes [MFC], OLE
- OLE common dialog classes [MFC]
- common dialog classes [MFC]
ms.assetid: 706526ae-f94f-4909-a0f8-6b5fe954fd97
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0617354337e75e2c2431df894c054722349e2306
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ole-common-dialog-classes"></a>Classes de boîtes de dialogue communes OLE
Ces classes gèrent les tâches courantes de OLE en implémentant un nombre de boîtes de dialogue OLE standard. Elles fournissent également une interface utilisateur cohérente pour les fonctionnalités OLE.  
  
 [COleDialog](../mfc/reference/coledialog-class.md)  
 Utilisé par l’infrastructure pour contenir les implémentations courantes pour toutes les boîtes de dialogue OLE. Toutes les classes de boîte de dialogue dans la catégorie de l’interface utilisateur sont dérivées de cette classe de base. `COleDialog`ne peut pas être utilisée directement.  
  
 [Classe COleInsertDialog](../mfc/reference/coleinsertdialog-class.md)  
 Affiche la boîte de dialogue Insérer un objet, l’interface utilisateur standard pour l’insertion de nouvelles OLE éléments liés ou incorporés.  
  
 [Classe COlePasteSpecialDialog](../mfc/reference/colepastespecialdialog-class.md)  
 Affiche la boîte de dialogue Collage spécial, l’interface utilisateur standard pour l’implémentation de la commande modifier le collage spécial.  
  
 [COleLinksDialog](../mfc/reference/colelinksdialog-class.md)  
 Affiche la boîte de dialogue Modifier les liaisons, l’interface utilisateur standard pour la modification des informations sur les éléments liés.  
  
 [Classe COleChangeIconDialog](../mfc/reference/colechangeicondialog-class.md)  
 Affiche la boîte de dialogue Changer d’icône, l’interface utilisateur standard pour la modification de l’icône associée à une OLE incorporé ou lié un élément.  
  
 [Classe COleConvertDialog](../mfc/reference/coleconvertdialog-class.md)  
 Affiche la boîte de dialogue de conversion, l’interface utilisateur standard pour la conversion des éléments OLE à partir d’un type.  
  
 [COlePropertiesDialog](../mfc/reference/colepropertiesdialog-class.md)  
 Encapsule la boîte de dialogue de propriétés OLE commune Windows. Boîtes de dialogue communes OLE propriétés fournissent un moyen simple pour afficher et modifier les propriétés d’un élément de document OLE de manière cohérente avec les normes de Windows.  
  
 [COleUpdateDialog](../mfc/reference/coleupdatedialog-class.md)  
 Affiche la boîte de dialogue de mise à jour, l’interface utilisateur standard pour mettre à jour tous les liens dans un document. La boîte de dialogue contient un indicateur de progression pour indiquer comment fermer la procédure de mise à jour est terminée.  
  
 [COleChangeSourceDialog](../mfc/reference/colechangesourcedialog-class.md)  
 Affiche la boîte de dialogue Modifier la Source, l’interface utilisateur standard pour la modification de la source d’un lien ou de destination.  
  
 [Classe COleBusyDialog](../mfc/reference/colebusydialog-class.md)  
 Affiche les boîtes de dialogue serveur occupé et serveur ne répond pas, l’interface utilisateur standard pour gérer les appels aux applications occupées. Généralement affiché automatiquement par le `COleMessageFilter` implémentation.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../mfc/class-library-overview.md)

