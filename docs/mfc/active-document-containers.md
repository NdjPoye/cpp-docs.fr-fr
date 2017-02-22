---
title: "Conteneurs de documents actifs | Microsoft Docs"
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
  - "documents actifs (conteneurs) (C++)"
  - "documents actifs (C++), conteneurs"
  - "conteneurs (C++), document actif"
  - "MFC COM (C++), documents actifs (contenance)"
ms.assetid: ba20183a-8b4c-440f-9031-e5fcc41d391b
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Conteneurs de documents actifs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un conteneur de documents actifs, comme Classeur Microsoft Office ou Internet Explorer, vous permet de travailler sur plusieurs documents de types différents d'application dans un seul cadre \(au lieu de votre application pour créer et utiliser des cadres de plusieurs applications pour chaque type de document\).  
  
 MFC prend en charge les conteneurs de documents actifs dans la classe de `COleDocObjectItem`.  Vous pouvez utiliser l'Assistant d'Application MFC pour créer un conteneur de documents actifs en activant la case à cocher de **Conteneur de documents actifs** sur la page de l'Assistant d'Application MFC **Mise en place de Documents Composés**.  Pour plus d'informations, consultez [Créer une application de conteneur de documents actifs](../mfc/creating-an-active-document-container-application.md).  
  
 Pour plus d'informations sur les conteneurs de documents actifs, consultez :  
  
-   [Spécifications de conteneur](#container_requirements)  
  
-   [Objets de site du document](#document_site_objects)  
  
-   [Objets du site de vue](#view_site_objects)  
  
-   [Objet de frame](#frame_object)  
  
-   [Fusion des menus Aide](../mfc/help-menu-merging.md)  
  
-   [Impression par programmation](../mfc/programmatic-printing.md)  
  
-   [Cibles de la commande](../mfc/message-handling-and-command-targets.md)  
  
##  <a name="container_requirements"></a> Spécifications de conteneur  
 La prise en charge des documents actifs dans un conteneur de documents actifs implique davantage que de simples implémentations d'interface : elle requiert également les connaissances d'utilisation des interfaces d'un objet contenu.  La même chose s'applique aux extensions de document actif, où le conteneur doit savoir utiliser ces interfaces d'extension pour les documents actifs eux\-mêmes.  
  
 Un conteneur de documents actifs qui intègre des documents actifs doit :  
  
-   Être capable de gérer le stockage d'objet via l'interface de **IPersistStorage** , c'est\-à\-dire qu'elle doit fournir une instance de `IStorage` à chaque document actif.  
  
-   Prendre en charge les fonctionnalités de base d'incorporation de documents OLE, ce qui nécessite des objets "sites" \(un par document ou incorporation\) qui implémentent **IOleClientSite** et **IAdviseSink**.  
  
-   Prendre en charge l'activation sur place des objets incorporés ou des documents actifs.  Les objets du site du conteneur doivent implémenter `IOleInPlaceSite` et l'objet cadre du conteneur doit fournir **IOleInPlaceFrame**.  
  
-   Prendre en charge les extensions de documents actifs en implémentant `IOleDocumentSite` pour fournir un mécanisme pour que le conteneur puisse parler au document.  Éventuellement, le conteneur peut implémenter les interfaces `IOleCommandTarget` et `IContinueCallback` de documents actifs pour exécuter des commandes simples telles que l'impression ou l'enregistrement.  
  
 L'objet cadre, les objets de la vue, et l'objet conteneur peuvent implémenter **IOleCommandTarget** pour prendre en charge la distribution de certaines commandes, comme décrit dans [Cible de la commande](../mfc/message-handling-and-command-targets.md).  La vue et les objets conteneur peuvent également implémenter `IPrint` et `IContinueCallback`, pour prendre en charge l'impression de programmation, comme décrit dans [Impression de programmation](../mfc/programmatic-printing.md).  
  
 L'illustration suivante montre les relations conceptuelles entre un conteneur et ses composants \(à gauche\), et entre le document actif et ses vues \(à droite\).  Le document actif gère le stockage et les données, et la vue affiche et éventuellement imprime ces données.  Les interfaces en gras sont celles requises pour la participation active de documents ; ceux en gras et italique sont optionnels.  Toutes les interfaces sont requises.  
  
 ![Interfaces actives de conteneurs de documents](../mfc/media/vc37gj1.png "vc37gj1")  
  
 Un document qui ne prend en charge qu'une vue peut implémenter à la fois le composant de vue et et celui de document \(autrement dit, les interfaces correspondantes\) sur une seule classe concrète.  En outre, un site du conteneur qui ne prend en charge qu'une vue à la fois peut combiner le site du document et le site de vue dans une classe unique concrète de site.  L'objet cadre du conteneur, toutefois, doit rester distinct, et le composant du document du conteneur est simplement inclus ici pour afficher une image complète de l'architecture ; il n'est pas affecté par l'architecture de la relation contenant\-contenu du document actif.  
  
##  <a name="document_site_objects"></a> Objets de site du document  
 Dans l'architecture de la relation contenant\-contenu du document actif, un site de document est le même qu'un objet de site client dans OLE Documents avec l'ajout de l'interface `IOleDocument`:  
  
 `interface IOleDocumentSite : IUnknown`  
  
 `{`  
  
 `HRESULT ActivateMe(IOleDocumentView *pViewToActivate);`  
  
 `}`  
  
 Le site du document est conceptuellement le conteneur pour un ou plusieurs objets « de site ».  Chaque objet de vue de site est associé à des objets de vue du document géré par le site du document.  Si le conteneur prend en charge une seule vue par site de document, il peut implémenter le site du document et le site de la vue avec une classe unique concrète.  
  
##  <a name="view_site_objects"></a> Objets du site de vue  
 L'objet de vue de site d'un conteneur gère l'espace d'une vue spécifique d'un document.  En plus de prendre en charge l'interface standard `IOleInPlaceSite`, un site de vue implémente également en général `IContinueCallback` pour le paramètre général de présentation de programmation. \(Remarquez que l'objet de vue ne demande jamais `IContinueCallback` pour qu'il puisse réellement être implémenté sur n'importe quel objet désiré par le conteneur.\)  
  
 Un conteneur qui prend en charge plusieurs vues doit pouvoir créer plusieurs objets de site de vue dans le site du document.  Cela permet à chaque vue des services distincts d'activation et de désactivation comme c'est fourni par `IOleInPlaceSite`.  
  
##  <a name="frame_object"></a> Objet de frame  
 L'objet cadre du conteneur est, en grande partie le même cadre qui est utilisé pour l'activation sur place dans OLE documents, c'est à dire celui qui gère les négociations de menu et de la barre d'outils.  Un objet de vue a accès à cet objet cadre à travers **IOleInPlaceSite::GetWindowContext**, ce qui donne également accès à l'objet conteneur qui représente le document conteneur \(qui peut gérer la négociation dau niveau du volet de la barre d'outils et l'énumération de l'objet contenu\).  
  
 Un conteneur de documents actifs peut augmenter le cadre en ajoutant `IOleCommandTarget`.  Cela lui permet de recevoir les commandes qui proviennent de l'interface utilisateur du document actif de la même façon que cette interface peut permettre à un conteneur d'envoyer les mêmes commandes \(telles que **Nouveau fichier**, **Ouvrir**, **Enregistrer sous**, **Imrpimer**; **Editer Copier**, **Coller**, **Annuler**, entre autres\) dans un document actif.  Pour plus d'informations sur les cibles, consultez [Cibles de Commandes](../mfc/message-handling-and-command-targets.md).  
  
## Voir aussi  
 [Relation contenant\-contenu de document actif](../mfc/active-document-containment.md)