---
title: "Classes de conteneur OLE | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classes ActiveX (C++)"
  - "classes de conteneur (C++)"
  - "conteneurs (C++), applications conteneur OLE"
  - "OLE (C++), classes"
  - "OLE (classes) (C++)"
  - "édition visuelle (C++), classes"
ms.assetid: 1e27e1ab-4c22-41eb-8547-6915c72668ae
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classes de conteneur OLE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ces classes sont utilisées par les applications conteneur.  `COleLinkingDoc` et `COleDocument` gèrent les collections d'objets `COleClientItem`.  Au lieu de dériver la classe de document de **CDocument**, vous le dériverez depuis `COleLinkingDoc` ou `COleDocument`, selon que vous souhaitez la prise en charge des liens vers des objets incorporés dans votre document.  
  
 Utilisez un objet `COleClientItem` pour représenter chaque élément OLE dans le document qui est incorporé à un autre document, ou qui est un lien vers un autre document.  
  
 [COleDocObjectItem](../mfc/reference/coledocobjectitem-class.md)  
 Prend en charge l'incorporation de documents actifs.  
  
 [COleDocument](../mfc/reference/coledocument-class.md)  
 Utilisé pour l'implémentation de document composite, ainsi que la prise en charge de base du conteneur.  Sert de conteneur aux classes dérivées de  `CDocItem`.  Cette classe peut être utilisée en tant que classe de base pour les documents conteneur et est la classe de base pour `COleServerDoc`.  
  
 [COleLinkingDoc](../mfc/reference/colelinkingdoc-class.md)  
 Une classe dérivée de `COleDocument` qui fournit l'infrastructure pour lier.  Vous pouvez dériver les classes de document pour vos applications conteneur depuis cette classe plutôt que depuis `COleDocument` si vous voulez qu'elles prennent en chargeles liens vers des objets incorporés.  
  
 [CRichEditDoc](../mfc/reference/cricheditdoc-class.md)  
 Contient la liste de clients OLE éléments contenus dans le contrôle RichEdit.  Utilisé avec [CRichEditView](../mfc/reference/cricheditview-class.md) et [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md).  
  
 [CDocItem](../mfc/reference/cdocitem-class.md)  
 Classe abstraite de `COleClientItem` et `COleServerItem`.  Les objets de classes dérivées de `CDocItem` représentent des parties de documents.  
  
 [COleClientItem](../mfc/reference/coleclientitem-class.md)  
 Une classe d'élément client qui représente le côté client de la connexion OLE à un élément incorporé ou lié.  Dérive les éléments clients depuis cette classe.  
  
 [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)  
 Fournit l'accès côté client à un élément OLE stocké dans un contrôle RichEdit en cas d'utilisation avec `CRichEditView` et `CRichEditDoc`.  
  
 [COleException](../mfc/reference/coleexception-class.md)  
 Une exception résultant d'une défaillance de traitement OLE.  Cette classe est utilisée par les conteneurs et les serveurs.  
  
## Voir aussi  
 [Vue d'ensemble des classes](../mfc/class-library-overview.md)