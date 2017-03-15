---
title: "Ordre des op&#233;rations pour la cr&#233;ation de contr&#244;les ActiveX | Microsoft Docs"
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
  - "contrôles ActiveX (C++), créer"
  - "contrôles ActiveX MFC (C++), créer"
  - "contrôles OLE (C++), MFC"
  - "séquence (C++)"
  - "séquence (C++), pour la création de contrôles ActiveX"
ms.assetid: 7d868c53-a0af-4ef6-a89c-e1c03c583a53
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Ordre des op&#233;rations pour la cr&#233;ation de contr&#244;les ActiveX
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le tableau suivant indique votre rôle et celuidu framework en créant des contrôles ActiveX \(anciennement appelé contrôles OLE\).  
  
### Création d'un contrôle ActiveX  
  
|Tâche|Vous faites|L'infrastructure fait|  
|-----------|-----------------|---------------------------|  
|Créez une infrastructure de contrôle ActiveX.|Exécutez l'Assistant de Contrôle ActiveX MFC pour créer le contrôle.  Spécifiez les options souhaitées dans les pages d'options.  Les options comprennent le type et le nom du contrôle dans le projet, licences, le sous\-classement, et une About Box.|L'assistant Contrôle ActiveX MFC crée les fichiers pour un contrôle ActiveX avec les fonctionnalités de base, y compris les fichiers sources pour votre application, contrôles, page ou pages de propriétés; un fichier de ressources ; un fichier projet ; tout étant adapté à vos fonctionnalités.|  
|Consultez ce que le contrôle et l'Assistant de Contrôle ActiveX offrent sans ajouter une ligne à votre propre code.|Génère le contrôle ActiveX et testez\-le avec Internet Explorer ou [Exemple de TSTCON](../top/visual-cpp-samples.md).|Le contrôle en cours d'exécution a la possibilité d'être redimensionné et déplacé.  Elle possède également une méthode **About Box** qui peut être appelée \(si sélectionnée\).|  
|Vous devez implémenter les méthodes et les propriétés.|Implémentez vos méthodes spécifiques à vos contrôles et propriétés en ajoutant des fonctions membres pour fournir une interface exposée aux données du contrôle.  Ajoutez les variables membres pour contenir les structures de données et utiliser des gestionnaires d'événements pour déclencher des événements lorsque vous le souhaitez.|Le framework a déjà défini une map pour prendre en charge les événements, propriétés, et méthodes du contrôle, ce qui vous permet de vous concentrer sur la façon dont les propriétés et les méthodes sont implémentées.  La page de propriétés par défaut est visible et une méthode About Box est par défaut est fournie.|  
|Créez la page de propriétés ou les pages du contrôle.|Utilisez les éditeurs de ressources Visual C\+\+ pour modifier visuellement l'interface de la page de propriétés du contrôle :<br /><br /> -   Créez les pages de propriétés supplémentaires.<br />-   Créer et modifier les images bitmap, les icônes, et les curseurs.<br /><br /> Vous pouvez également tester la page de propriétés dans l'éditeur de boîtes de dialogue.|Le fichier de ressources par défaut créé par l'Application MFC fournit plusieurs ressources dont vous avez besoin.  Visual C\+\+ vous permet de modifier les ressources existantes et d'ajouter de nouvelles ressources facilement et visuellement.|  
|Testez les événements, les méthodes, les propriétés et du contrôle.|Reconstruisez le contrôle et l'utilisation de Test Container de vérifier que les gestionnaires fonctionnent correctement.|Vous pouvez appeler les méthodes de contrôle et manipuler les propriétés par le biais de l'interface de page de propriétés ou via le Test Container.  En outre, utilisez Test Container pour suivre les événements déclenchés par le contrôle et les notifications reçues par le conteneur du contrôle.|  
  
## Voir aussi  
 [Génération à partir du Framework](../mfc/building-on-the-framework.md)   
 [Ordre des opérations pour la génération d'applications MFC](../mfc/sequence-of-operations-for-building-mfc-applications.md)   
 [Ordre des opérations pour la création d'applications OLE](../mfc/sequence-of-operations-for-creating-ole-applications.md)   
 [Ordre des opérations pour la création d'applications de base de données](../mfc/sequence-of-operations-for-creating-database-applications.md)