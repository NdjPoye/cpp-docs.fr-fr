---
title: "Arri&#232;re-plan OLE | Microsoft Docs"
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
  - "OLE, à propos de OLE"
ms.assetid: 5f654eb5-66b1-40c9-9215-bb85356a67f8
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Arri&#232;re-plan OLE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

OLE est un mécanisme qui permet aux utilisateurs de créer et modifier des documents contenant des éléments ou "objets" créés par plusieurs applications.  
  
> [!NOTE]
>  OLE était à l'origine un acronyme pour la liaison et incorporation d'objets.  Toutefois, il est maintenant appelé OLE.  Les parties OLE non liées à la liaison et l'incorporation font partie de la technologie active.  
  
 Les documents OLE, historiquement appelés documents composés, intègrent de façon transparente des types de données, ou composants.  Des clips audio, les feuilles de calcul, et les bitmaps sont des exemples typiques des composants détectés dans OLE documents.  La prise en charge OLE dans votre application permet aux utilisateurs d'utiliser OLE de documents sans vous préoccuper de basculement entre les différentes applications ; OLE effectue le basculement pour vous.  
  
 Vous utilisez une application conteneur de créer des documents composés et une application serveur ou sur une application du composant de création d'éléments dans le document conteneur.  Toute application que vous écrivez peut être un conteneur, un serveur, ou les deux.  
  
 OLE incorpore différents concepts que tout le travail vers l'objectif de l'interaction transparente entre les applications.  Ces zones incluent ce qui suit:  
  
 Liaison et incorporation  
 La liaison et l'incorporation sont les deux méthodes pour stocker les éléments créés dans un document OLE créé dans une autre application.  Pour obtenir des informations générales sur les différences entre les deux, consultez l'article [OLE arrière\-plan : Liaison et incorporation](../mfc/ole-background-linking-and-embedding.md).  Pour plus d'informations, consultez les articles [Conteneurs](../mfc/containers.md) et [Serveurs](../mfc/servers.md).  
  
 Activation sur place \(modification sur place\)  
 L'activation d'un élément incorporé dans le contexte du document conteneur est appelé activation sur place ou modification sur place.  L'interface de l'application change afin d'incorporer les fonctionnalités de l'application du composant qui a créé l'élément incorporé.  Les éléments liés ne sont jamais activés en place car les données réelles pour l'élément sont contenues dans un fichier distinct, hors de le contexte de l'application qui contient le lien.  Pour plus d'informations sur l'activation sur place, consultez l'article [Activation](../mfc/activation-cpp.md).  
  
> [!NOTE]
>  La liaison et l'incorporation et l'activation sur place fournissent les fonctionnalités principales d'OLE la modification sur place.  
  
 Automation  
 L'automatisation permet à une application de piloter une autre application.  L'application pilotante correspond à un client Automation, et l'application qui est contrôlée est appelé serveur Automation ou un composant automation.  Pour plus d'informations sur l'automation, consultez les articles [Clients Automation](../mfc/automation-clients.md) et [Serveurs Automation](../mfc/automation-servers.md).  
  
> [!NOTE]
>  L'automation s'exécute dans les contextes OLE et de technologie Active.  Vous pouvez automatiser un objet basé sur COM.  
  
 Fichiers Composés  
 Les fichiers composites fournissent un format de fichier standard qui simplifie le stockage structuré de documents composés pour les applications OLE.  Dans un fichier composé, le stockage ont de nombreuses fonctionnalités de répertoires et les flux de données ont de nombreuses fonctionnalités de fichiers.  Cette technologie est également appelée stockage structuré.  Pour plus d'informations sur les fichiers composites, consultez l'article [Conteneurs : Fichiers composites](../mfc/containers-compound-files.md).  
  
 Transfert uniforme de données  
 Le transfert uniforme de données \(UDT\) est un ensemble d'interfaces qui fournissent des données à envoyer et être reçus en mode standard, quelle que soit la méthode choisie réelle pour transférer les données.  L'UDT constitue la base des transferts de données par le glisser\-déplacer.  UDT sert de base pour transférer des données Windows existantes, tel que le presse\-papiers et l'échange dynamique de données \(DDE\).  Pour plus d'informations sur UDT, consultez l'article [Objets de données et sources de données \(OLE\)](../mfc/data-objects-and-data-sources-ole.md).  
  
 Glisser\-déplacer  
 Glisser\-déposer est une technique simple d'utilisation, de manipulation directe de transfert des données entre les applications, des fenêtres dans une application, ou même dans une fenêtre unique dans une application.  Les données à transférer sont sélectionnées et déposées à la destination souhaitée.  Glisser\-déposer est basé sur le transfert de données uniforme.  Pour plus d'informations sur le glisser\-déplacer, consultez l'article [Glisser\-déplacer](../mfc/drag-and-drop-ole.md).  
  
 Component Object Model  
 Le modèle COM \(component object model \(COM\) fournit l'infrastructure utilisée lorsque les objets OLE communiquent entre eux.  Les classes OLE MFC simplifient COM du programmeur.  COM fait partie de la technologie active, car les objets COM sont de la OLE et la technologie.  Pour plus d'informations sur COM, consultez les rubriques [ATL \(ATL\)](../atl/active-template-library-atl-concepts.md).  
  
 Certains OLE rubriques plus importants sont traitées dans les éléments suivants :  
  
-   [Arrière\-plan OLE : liaison et incorporation](../mfc/ole-background-linking-and-embedding.md)  
  
-   [Arrière\-plan OLE : conteneurs et serveurs](../mfc/ole-background-containers-and-servers.md)  
  
-   [Arrière\-plan OLE : stratégies d'implémentation](../mfc/ole-background-implementation-strategies.md)  
  
-   [Arrière\-plan OLE : implémentation MFC](../mfc/ole-background-mfc-implementation.md)  
  
 Pour OLE les informations de général manquants dans les éléments ci\-dessus, recherchez OLE dans MSDN.  
  
## Voir aussi  
 [OLE](../mfc/ole-in-mfc.md)