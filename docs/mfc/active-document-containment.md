---
title: "Relation contenant-contenu de document actif | Microsoft Docs"
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
  - "documents actifs (conteneurs) (C++), à propos des conteneurs de documents actifs"
  - "documents actifs (C++), conteneurs"
  - "conteneurs (C++), document actif"
  - "MFC (C++), prise en charge COM"
  - "MFC COM (C++), documents actifs (contenance)"
ms.assetid: b8dfa74b-75ce-47df-b75e-fc87b7f7d687
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Relation contenant-contenu de document actif
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

la limitation de document actif est une technologie qui fournit une unique fenêtre dans laquelle on travaille avec les documents, au lieu de forcer à créer et à utiliser plusieurs fenêtres de l'application pour chaque type de document.  Cela diffère des technologies basiques d'OLE dans le sens qu'OLE marche avec des objets intégrés dans un document composé dans lequel une unique partie du contenu peut\-être active.  Avec la limitation de document actif, vous activez un document entier \(c'est\-à\-dire une application entière, incluant des menus associés, des barres d'outils,...\) dans le contexte d'une unique fenêtre.  
  
 La technologie d'endiguement de document actif fut à l'origine développée pour Microsoft Office pour implémenter Office Binder.  Cependant, la technologie est suffisamment flexible pour supporter d'autres conteneurs de documents actifs qu'Office Binder, et peut supporter des serveurs de documents autre qu'Office et les applications compatibles avec Office.  
  
 L'application qui héberge les documents actifs est appelée un [conteneur de documents actifs](../mfc/active-document-containers.md).  Des exemple de tels conteneurs sont Microsft Office Binder ou Microsoft Internet Explorer.  
  
 la limitation de documents actifs est implémenté comme une série d'extensions de documents OLE, la technologie de documents intégrés d'OLE.  Les extensions sont à présent des interfaces additionnelles qui permettent à un objet intégrable de représenter un document tout entier au lieu d'une simple partie du contenu intégré.  De la même façon qu'avec les documents OLE, l'endiguement de documents actifs utilise un conteneur qui fournit l'espace d'affichage des documents actifs, et les serveurs qui fournissent l'interface utilisateur et les capacités de manipulations pour les documents actifs eux\-mêmes.  
  
 Un [serveur de documents actifs](../mfc/active-document-servers.md) est une application \(telle que Word, Excel ou Powerpoint\) qui supporte une ou plusieurs calsses de documents actifs, où chaque objet supporte lui\-même les interfaces d'extensions qui permettent d'activer l'objet dans un conteneur convenable.  
  
 Un [document actif](../mfc/active-documents.md) \(fournit depuis un serveur de documents actifs tel que Word ou Excel\) est essentiellement un document conventionnel à part entière, qui est intégré comme objet dans un autre conteneur de documents actifs.  A la différence de ces objets intégrés, les documents actifs ont un contrôle complet sur leurs pages, et l'interface entière de l'application \(avec toutes ses commandes et ses outils\) est mise à la disposition des utilisateurs qui peuvent les éditer.  
  
 La façon la plus facile de comprendre un document actif est de le distinguer d'un objet intégré OLE standard.  Suivant la convention OLE, un objet intégré est un objet qui est affiché dans la page du document auquel il appartient, et le document est géré par un conteneur OLE.  The container stores the embedded object's data with the rest of the document.  Cependant, les objets intégrés sont limités car ils ne contrôlent pas la page sur laquelle ils apparaîssent.  
  
 Les utilisateurs d'une application de limitation de document peuvent créer des documents actifs \(appelés sections dans Office Binder\) en utilisant leurs applications préférées \(si ces applications sont capables de gérer les documents actifs\), et l'utilisateur peut gérer le projet résultant en tant qu'une unique entité, qui peut être nommée, sauvegardée, imprimée, etc. de façon unique.  De la même façon, un utilisateur d'un navigateur internet peut traiter le réseau tout entier, ainsi que les fichiers locaux, en tant qu'une unique entité de stockage qui a la capacité de parcourir les documents de ce stock depuis un unique endroit.  
  
## Des exemples de Programmes  
  
-   L'exemple [MFCBIND](../top/visual-cpp-samples.md) illustre l'implémentation d'une application de limitation de documents actifs.  
  
## Voir aussi  
 [MFC COM](../mfc/mfc-com.md)