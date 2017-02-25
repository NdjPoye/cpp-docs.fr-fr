---
title: "Gestion des donn&#233;es avec variables de donn&#233;es de document | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classes (C++), friend"
  - "classes de collection (C++), utilisées par l'objet document"
  - "données (MFC)"
  - "données (MFC), documents"
  - "données de document (C++)"
  - "documents (C++), stockage des données"
  - "friend (classes)"
  - "variables membres (C++), classe de document"
ms.assetid: e70b87f4-8c30-49e5-8986-521c2ff91704
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Gestion des donn&#233;es avec variables de donn&#233;es de document
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Implémente des données de votre document comme variables membres de votre document fichier.  Par exemple, le programme de dessin à la main levée déclare un membre de données de type `CObList` — une liste liée qui stocke des pointeurs sur les objets d'`CObject`.  Cette liste permet de stocker les options de points qui forment un dessin du trait à la main levée.  
  
 Comment implémenter les données de membre de votre document dépend de la nature de votre application.  Pour dépanner, MFC fournit un groupe de « classes de collection » — tables, listes, et cartes \(dictionnaires\), notamment les collections basées sur des modèles C\+\+ \)avec des classes qui encapsulent divers types de données communes comme `CString`, `CRect`, `CPoint`, `CSize`, et `CTime`.  Pour plus d'informations sur ces classes, consultez [Présentation de la bibliothèque de classes](../mfc/class-library-overview.md) dans *le guide de MFC*.  
  
 Lorsque vous définissez les données de membre de votre document, vous ajouterez généralement les fonctions membres à la classe de document pour définir et récupérer des éléments de données et effectuer d'autres opérations utiles sur elles.  
  
 Les vues accèdent à l'objet document à l'aide du pointeur sur le document, installé dans la vue lors de la création.  Vous pouvez récupérer ce pointeur dans les fonctions membres d'une vue en appelant la fonction membre **GetDocument**d'`CView`.  Veillez à convertir ce pointeur vers votre propre type de document.  Vous pouvez accéder aux membres de document public par le pointeur.  
  
 Si le transfert de données fréquente nécessite un accès direct, ou si vous voulez utiliser les membres non publics de la classe de document, vous pouvez transformer votre classe d'affichage en une fonction friend \(en termes de C\+\+\) de la classe de document.  
  
## Voir aussi  
 [Utilisation de documents](../mfc/using-documents.md)