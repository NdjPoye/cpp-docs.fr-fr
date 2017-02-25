---
title: "Classes de contr&#244;le OLE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
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
  - "classes de contrôle ActiveX (C++)"
  - "contrôles ActiveX (C++), classes de contrôle OLE"
  - "contrôles personnalisés (MFC), classes"
  - "classes de contrôle OLE (C++)"
  - "contrôles OLE (C++), classes"
  - "classes de composant réutilisable"
ms.assetid: 96495ec3-319e-4163-b839-1af0428ed9dd
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Classes de contr&#244;le OLE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Voici les principales classes que vous utilisez lorsque vous entrez des contrôles OLE.  La classe de `COleControlModule` dans un module de contrôle OLE est similaire à la classe de [CWinApp](../mfc/reference/cwinapp-class.md) dans une application.  Chaque module implémente un ou plusieurs vérifications OLE ; ces contrôles sont représentés par des objets de `COleControl`.  Ces contrôles communiquent avec leurs conteneurs à l'aide de objets de `CConnectionPoint`.  
  
 Les classes de `CPictureHolder` et de `CFontHolder` encapsulent les interfaces COM des images et des polices, tandis que les classes de `COlePropertyPage` et de `CPropExchange` vous aident pour implémenter les pages de propriétés et la persistance de propriété pour votre contrôle.  
  
 [COleControlModule](../mfc/reference/colecontrolmodule-class.md)  
 Remplace la classe de `CWinApp` pour votre module de contrôle OLE.  Dérive de la classe de `COleControlModule` pour développer un objet de module de contrôle OLE.  Il fournit des fonctions de membre pour initialiser le module de votre contrôle OLE.  
  
 [COleControl](../mfc/reference/colecontrol-class.md)  
 Dériver de la classe de `COleControl` pour développer un contrôle OLE.  Dérivé de `CWnd`, cette classe hérite de toutes les fonctionnalités d'un objet fenêtre Windows et des fonctionnalités supplémentaires de OLE\-fonctionnalité supplémentaires, tel que le déclenchement d'événements et la capacité de prendre en charge des méthodes et des propriétés.  
  
 [CConnectionPoint](../mfc/reference/cconnectionpoint-class.md)  
 Le `CConnectionPoint` définit un type particulier d'interface utilisé pour communiquer avec d'autres objets OLE, appelé « point de connexion ».  Un point de connexion implémente une interface sortante qui peut initier des actions sur d'autres objets, tels que les événements d'activation et les notifications de modification.  
  
 [CPictureHolder](../mfc/reference/cpictureholder-class.md)  
 Encapsule les fonctionnalités d'un objet image windows et l'interface de `IPicture` COM ; utilisé pour implémenter la propriété image personnalisée d'un contrôle OLE.  
  
 [CFontHolder](../mfc/reference/cfontholder-class.md)  
 Encapsule la fonctionnalité d'une police de caractère d'un objet Windows et l'interface de `IFont` COM; Utilisé pour implémenter l'approvisionnement de la propriété de la police de caractère d'un contrôle OLE.  
  
 [COlePropertyPage](../mfc/reference/colepropertypage-class.md)  
 Affiche les propriétés d'un contrôle OLE dans une interface graphique, similaire à une fenêtre de dialogue.  
  
 [CPropExchange](../mfc/reference/cpropexchange-class.md)  
 Prend en charge l'implémentation de la propriété de vos contrôles OLE.  Analogue à [CDataExchange](../mfc/reference/cdataexchange-class.md) pour les boîtes de dialogue.  
  
 [CMonikerFile](../mfc/reference/cmonikerfile-class.md)  
 Prend un moniker, une représentation de chaîne qu'il peut traiter dans moniker, et il le lie de façon synchrone au flux de données pour lequel le moniker est un nom.  
  
 [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)  
 Fonctionne de manière similaire à `CMonikerFile`; toutefois, il lie le moniker asynchrone au flux de données pour lequel le moniker est un nom.  
  
 [CDataPathProperty](../mfc/reference/cdatapathproperty-class.md)  
 Implémente une propriété de contrôle OLE qui peut être chargée de façon asynchrone.  
  
 [CCachedDataPathProperty](../mfc/reference/ccacheddatapathproperty-class.md)  
 Implémente une propriété de contrôle OLE transférée de façon asynchrone et mise en cache dans un fichier de mémoire.  
  
 [COleCmdUI](../mfc/reference/colecmdui-class.md)  
 Permet à un document actif d'accepter les commandes qui proviennent de l'interface utilisateur de son conteneur \(notamment FileNew, ouvrez, copie, etc.\), mais permet à un conteneur d'accepter les commandes qui proviennent de l'interface utilisateur du document actif.  
  
 [COleSafeArray](../mfc/reference/colesafearray-class.md)  
 Travailler pour utiliser des tableaux de type et de dimension arbitraires.  
  
## Voir aussi  
 [Vue d'ensemble des classes](../mfc/class-library-overview.md)