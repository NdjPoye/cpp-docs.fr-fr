---
title: "MFC COM | Microsoft Docs"
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
  - "MFC COM (MFC)"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "technologie active (C++)"
  - "contrôles ActiveX (C++), modèle objet COM"
  - "COM (C++), prise en charge des MFC"
  - "MFC (C++), prise en charge COM"
  - "contrôles ActiveX MFC (C++), prise en charge COM dans les MFC"
  - "MFC COM (C++)"
ms.assetid: 7646bdcb-3a06-4ed5-9386-9b00f3979dcb
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC COM
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un sous\-ensemble de MFC est conçu pour prendre en charge COM, alors que la majeure partie de l'ATL \(Active Template Library\) est conçue pour la programmation COM.  Cette section de la rubrique décrit la prise en charge de COM par MFC.  
  
 Les technologies actives \(telles que les contrôles ActiveX, la relation contenant\-contenu de document actif, OLE, etc.\) utilisent le modèle COM \(component object model \(COM\) pour permettre aux composants logiciels pour communiquer entre eux dans un environnement réseau, quel que soit le langage dans lequel ils ont été créés.  Des technologies actives peuvent être utilisées pour créer des applications exécutées sur le bureau ou Internet.  Pour plus d'informations consultez [Introduction à COM](../atl/introduction-to-com.md) ou [Le component object model\)](http://msdn.microsoft.com/library/windows/desktop/ms694363).  
  
 Les technologies actives incluent les deux technologies clientes et serveur, notamment :  
  
-   [La relation contenant\-contenu de document actif](../mfc/active-document-containment.md), prise en charge dans les versions 4.2 de MFC et les versions ultérieures, permet aux utilisateurs d'afficher des [documents actifs](../mfc/active-documents.md) \(tels que des fichers Microsoft Excel ou Word\) et activer l'interface entière de l'application native du document dans la zone du client du [conteneur de documents actifs](../mfc/active-document-containers.md) comme le Classeur Microsoft Office ou Microsoft Internet Explorer.  Les conteneurs se comportent comme des clients, tandis que les documents sont fournis par des [serveurs de documents actifs](../mfc/active-document-servers.md).  Pour plus d'informations sur l'utilisation des documents actifs dans les applications Web, consultez : [Documents actifs sur Internet](../mfc/active-documents-on-the-internet.md).  
  
-   Les contrôles ActiveX sont des objets interactifs qui peuvent être utilisés dans des conteneurs tels qu'un site Web.  Pour plus d'informations sur les contrôles ActiveX, consultez :  
  
    -   [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)  
  
    -   [Contrôles ActiveX sur Internet](../mfc/activex-controls-on-the-internet.md)  
  
    -   [Vue d'ensemble : Internet](../mfc/mfc-internet-programming-basics.md)  
  
    -   [Mettre à niveau un contrôle ActiveX existant qui sera utilisé sur Internet](../mfc/upgrading-an-existing-activex-control.md)  
  
    -   [déboguer des contrôles ActiveX](../Topic/How%20to:%20Debug%20an%20ActiveX%20Control.md)  
  
-   La création de scripts actifs contrôle le comportement intégré d'un ou plusieurs contrôles ActiveX d'un navigateur ou d'un serveur.  Pour plus d'informations sur la création de scripts actif, consultez [Technologie active sur Internet](../mfc/active-technology-on-the-internet.md).  
  
-   [Automation](../mfc/automation.md) \(anciennement appelé OLE Automation\) permet à une application de manipuler des objets implémentés dans une autre application, ou d'"exposer" des objets pour qu'ils puissent être manipulés.  
  
     L'objet automatisé peut être local ou [distant](../mfc/remote-automation.md) \(sur un ordinateur accessible sur un réseau\).  Automation est disponible pour les objets OLE et COM.  
  
-   Cette section fournit également des informations sur la façon d'écrire les composants COM  en utilisant MFC, par exemple, dans des [Points de connexion](../mfc/connection-points.md).  
  
 Pour une présentation de ce qui est toujours appelé OLE par rapport à ce qui est maintenant appelé technologie active, consultez les rubriques de [OLE](../mfc/ole-in-mfc.md).  
  
 En outre, consultez l'article de la Base de connaissances Q248019 : HOWTO : Empêcher une boîte de dialogue de serveur occupé d'apparaître lors d'une opération longue COM.  
  
## Dans cette section  
 [Relation contenant\-contenu de document actif](../mfc/active-document-containment.md)  
  
 [Automation](../mfc/automation.md)  
  
 [automation à distance](../mfc/remote-automation.md)  
  
 [Points de connexion](../mfc/connection-points.md)  
  
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)  
  
## Voir aussi  
 [Concepts](../mfc/mfc-concepts.md)