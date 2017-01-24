---
title: "Documents actifs sur Internet | Microsoft Docs"
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
  - "documents actifs (C++), créer"
  - "documents actifs (C++), étapes de programmation"
  - "documents actifs (C++), utiliser les Assistants Application"
  - "Assistants Application (C++)"
  - "Assistants Application (C++), documents actifs"
ms.assetid: a46bd8a0-e27a-4116-b1bf-dacdb7ae78d1
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Documents actifs sur Internet
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les documents actifs fournissent une extension aux objets incorporés traditionnels.  Les documents actifs peuvent être multipages et apparaissent dans la zone du client.  Elles présentent la négociation traditionnelle de menu, et peuvent être sur place modifié ainsi que dans une fenêtre active de l'application serveur.  Au lieu d'afficher comme un petit rectangle entouré par une bordure hachée, les documents actifs sont des cadres complets et activés toujours sur place.  
  
 Les documents actifs peuvent être affichés dans un conteneur comme Classeur Microsoft Office, qui permet de créer un document composite composée de différents types de document comme Excel, express, et le type de document personnalisé, qui peut être le cadre complet modifié.  Les documents actifs peuvent également être affichés dans un navigateur tel que Microsoft Internet Explorer, qui est un conteneur de documents actifs.  
  
 **Les avantages de document actif sont les suivantes :**  
  
-   Les documents peuvent être des cadres complets affichés, dans la fenêtre cliente entière.  
  
-   Les documents peuvent être ouverts dans une fenêtre d'application séparée.  
  
     Pour que le document s'ouvre, l'application d'assistance doit exister sur le client ou bien être téléchargée séparément avant que l'application puisse s'exécuter.  Une visionneuse peut être écrite pour fournir des fonctionnalités limitées \(word, PowerPoint, et Excel fournissent des visionneuses pour les documents\).  La version complète de l'application peut fournir une prise en charge totale de modification.  
  
-   Les documents sont toujours actifs sur place.  
  
-   Les commandes de menu appelées du conteneur peuvent être routées vers votre document.  
  
-   Les documents peuvent être affichés dans un navigateur Web.  Cela fournit l'intégration transparente entre vos documents et d'autres pages Web.  
  
     Un utilisateur peut rechercher une page Web HTML, puis une feuille de calcul Excel, puis à un document que vous avez entré à la prise en charge MFC pour les documents actifs.  L'utilisateur peut accéder à l'interface familière Web, comme les commutateurs de navigateur de façon transparente entre les menus et les vues d'une page HTML, Excel, puis le document de votre application.  
  
-   Toutes les applications dans un cadre commun.  
  
## Conditions requises pour les documents actifs  
 Les interfaces répertoriées dans le tableau ci\-dessous sont déjà les interfaces requises pour les serveurs incorporés et plusieurs nouvelles interfaces spécifiques aux documents actifs.  MFC offre des implémentations conformes par défaut pour la plupart des interfaces de la classe de [COleServerDoc](../mfc/reference/coleserverdoc-class.md).  
  
|Un document que…|Implémente ces interface .|  
|----------------------|--------------------------------|  
|Utilise des fichiers composites comme mécanisme de stockage.|`IPersistStorage`.|  
|Supporte les fonctionnalités de base d'incorporation de Active documents, y compris Créer Depuis un Fichier|`IPersistFile`, `IOleObject` et `IDataObject`.|  
|Support d'activation sur place|`IOleInPlaceObject` et `IOleInPlaceActiveObject` \(à `IOleInPlaceSite` du conteneur et les interfaces de **IOleInPlaceFrame** \).|  
|Prend en charge les extensions de document actif qui impliquent les nouvelles interfaces.  Des interfaces sont facultatives.|`IOleDocument`, `IOleDocumentView`, `IOleCommandTarget` et `IPrint`.|  
  
 MFC fournit la prise en charge d'étendre la prise en charge incorporée existante du serveur aux documents actifs.  
  
## Ajouter la prise en charge des documents actifs à une application  
 Pour créer une application avec prise en charge des documents actifs : Dans l'Application MFC, dans la page de **Prise en charge doc. composés**, sous « activez la prise en charge du document composite » choisissez **Full\-server** ou **Container\/Full\-server**, puis sous « sélectionnez d'autres options » activez la case à cocher pour **Serveur de documents actifs**.  
  
##  <a name="_core_convert_an_existing_mfc_in.2d.process_server_to_an_activex_document_server"></a> Convertir un serveur in\-process existant de MFC à un serveur de document actif  
 Si votre application a été créée avec une version de Visual C\+\+ avant la version 4,2 et est déjà un serveur in\-process, vous pouvez ajouter la prise en charge des documents actifs qui apporte des modifications aux classes suivantes :  
  
|Type de classe|Anciennement dérivé|Modifiez pour dériver de|  
|--------------------|-------------------------|------------------------------|  
|Cadre sur place|`COleIPFrameWnd`|**COleDocIPFrameWnd**|  
|Élément|`COleServerItem`|`CDocObjectServerItem`|  
  
 Vous allez également changer la façon dont les informations sont écrites dans le Registre, et apporterez à plusieurs autres des modifications.  Si votre application n'est actuellement pas prise en charge des composants COM, vous pouvez ajouter la prise en charge de serveur en exécutant l'Application et l'intégration code propre au composant COM avec votre application existante.  
  
## Voir aussi  
 [Tâches de programmation Internet MFC](../mfc/mfc-internet-programming-tasks.md)   
 [Éléments fondamentaux relatifs à la programmation Internet MFC](../mfc/mfc-internet-programming-basics.md)