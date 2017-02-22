---
title: "Classes de documents | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.document"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classes de documents"
ms.assetid: 4bf19b02-0a4f-4319-b68e-cddcba2705cb
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Classes de documents
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Documenter les objets de classe, créés par les objets modèle de document, gérer les données d'application.  Vous dériverez une classe pour vos documents de l'une de ces classes.  
  
 Les objets de classe de document interagissent avec les objets de vue.  Les objets de vue représentent la zone client d'un point, affichent les données d'un document, et permettent aux utilisateurs d'interagir avec elles.  Les documents et les vues sont créées par un objet modèle de document.  
  
 [CDocument](../mfc/reference/cdocument-class.md)  
 La classe de base pour les documents spécifiques à l'application.  Dérivez votre \(vos\) classe\(s\) de document de **CDocument**.  
  
 [COleDocument](../mfc/reference/coledocument-class.md)  
 Utilisé pour l'implémentation de document composite, ainsi que la prise en charge de base du conteneur.  Sert de conteneur aux classes dérivées de [CDocItem](../mfc/reference/cdocitem-class.md).  Cette classe peut être utilisée en tant que classe de base pour les documents conteneur et est la classe de base pour `COleServerDoc`.  
  
 [COleLinkingDoc](../mfc/reference/colelinkingdoc-class.md)  
 Une classe dérivée de `COleDocument` qui fournit l'infrastructure pour lier.  Vous devriez dériver les classes de document pour vos applications conteneur depuis cette classe plutôt que depuis `COleDocument` si vous voulez qu'elles prennent en charge les liens vers des objets incorporés.  
  
 [CRichEditDoc](../mfc/reference/cricheditdoc-class.md)  
 Contient la liste de clients OLE éléments contenus dans le contrôle RichEdit.  Utilisé avec [CRichEditView](../mfc/reference/cricheditview-class.md) et [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md).  
  
 [COleServerDoc](../mfc/reference/coleserverdoc-class.md)  
 Utilisé en tant que classe de base pour la classe de document d'application serveur.  Les objets `COleServerDoc` fournissent la majeure partie de la prise en charge de serveur via des interactions avec des objets [COleServerItem](../mfc/reference/coleserveritem-class.md).  La fonction de modification visuelle est fournie en utilisant l'architecture document\/vue de la bibliothèque de classes.  
  
 [CHtmlEditDoc](../mfc/reference/chtmleditdoc-class.md)  
 Fournit, avec [CHtmlEditView](../mfc/reference/chtmleditview-class.md), les fonctionnalités de la plateforme d'édition HTML WebBrowser au sein du contexte de l'architecture document\/vue de MFC.  
  
## Classes liées  
 Les objets de classe de document peuvent être persistants — en d'autres termes, ils peuvent écrire l'état dans un support de stockage et l'y relire.  MFC fournit la classe `CArchive` pour faciliter le transfert des données du document dans un support de stockage.  
  
 [CArchive](../mfc/reference/carchive-class.md)  
 Collabore avec un objet [CFile](../mfc/reference/cfile-class.md) pour implémenter le stockage permanent pour les objets de la sérialisation \(voir [CObject::Serialize](../Topic/CObject::Serialize.md)\).  
  
 Les documents peuvent également contenir des objets OLE.  `CDocItem` est la classe de base du serveur et des éléments client.  
  
 [CDocItem](../mfc/reference/cdocitem-class.md)  
 Classe de base abstraite [COleClientItem](../mfc/reference/coleclientitem-class.md) et [COleServerItem](../mfc/reference/coleserveritem-class.md).  Les objets de classes dérivées de `CDocItem` représentent des parties de documents.  
  
## Voir aussi  
 [Vue d'ensemble des classes](../mfc/class-library-overview.md)