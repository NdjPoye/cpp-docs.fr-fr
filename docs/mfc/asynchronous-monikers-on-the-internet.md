---
title: "Monikers asynchrones sur Internet | Microsoft Docs"
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
  - "contrôles ActiveX (C++), asynchrones"
  - "monikers asynchrones (C++)"
  - "télécharger des ressources Internet et des monikers asynchrones"
  - "Internet (C++), téléchargement asynchrone"
  - "MFC (C++), monikers asynchrones"
  - "optimisation (C++), téléchargement asynchrone sur Internet"
  - "applications Web (C++), asynchrones"
ms.assetid: 418b0c64-0046-4dae-8118-c9c762b5822e
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Monikers asynchrones sur Internet
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Internet nécessite de nouvelles approches pour la conception d'applications en raison de son accès réseau lent.  Les applications doivent réaliser un accès réseau asynchrone pour éviter de bloquer l'interface utilisateur.  La classe MFC [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) fournit la prise en charge asynchrone de téléchargement de fichiers.  
  
 Avec des monikers asynchrones, vous pouvez étendre votre application COM pour télécharger de façon asynchrone sur Internet et pour fournir un rendu progressif des objets larges tels que des images bitmap et des objets de VRML.  Des monikers asynchrones permettent à une propriété du contrôle ActiveX ou un fichier sur Internet d'être téléchargé sans bloquer la réponse de l'interface utilisateur.  
  
## Avantages des monikers asynchrones  
 Vous pouvez utiliser des monikers asynchrones pour :  
  
-   Télécharger du code et des fichiers sans blocage.  
  
-   Télécharger des propriétés dans les contrôles ActiveX sans blocage.  
  
-   Recevoir des notifications sur la progression du téléchargement.  
  
-   Suivez la progression et des informations d'état prêtes.  
  
-   Fournissez les informations d'état à l'utilisateur sur la progression.  
  
-   Autorisez l'utilisateur à annuler un téléchargement à tout moment.  
  
## Classes MFC des monikers asynchrones  
 [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) est dérivé de [CMonikerFile](../mfc/reference/cmonikerfile-class.md), qui à son tour est dérivé de [COleStreamFile](../mfc/reference/colestreamfile-class.md).  Un objet `COleStreamFile` représente un flux de données ; un objet `CMonikerFile` utilise `IMoniker` pour obtenir les données, et un objet `CAsyncMonikerFile` le fait de façon asynchrone.  
  
 Des monikers asynchrones sont utilisés principalement dans des applications Internet et des contrôles ActiveX pour fournir une interface utilisateur réactive pendant les transferts de fichiers.  Un exemple classique de cela est l'utilisation de [CDataPathProperty](../mfc/reference/cdatapathproperty-class.md) pour fournir des propriétés asynchrones aux contrôles ActiveX.  
  
## Classes MFC pour les chemins de données dans les contrôles ActiveX  
 Les classes MFC `CDataPathProperty` et [CCachedDataPathProperty](../mfc/reference/ccacheddatapathproperty-class.md) implémentent les propriétés du contrôle ActiveX qui peuvent être chargées de façon asynchrone.  Les propriétés asynchrones sont chargées après le lancement synchrone.  Les contrôles ActiveX asynchrones appellent à plusieurs reprises un rappel pour indiquer la disponibilité de nouvelles données au cours d'un processus long d'échange de propriétés.  
  
 `CDataPathProperty` est dérivé de `CAsyncMonikerFile`.  `CCachedDataPathProperty` est dérivé de `CDataPathProperty`.  Pour implémenter des propriétés asynchrones dans vos contrôles ActiveX, dérivez une classe `CDataPathProperty` ou `CCachedDataPathProperty`, puis remplacez [OnDataAvailable](../Topic/CAsyncMonikerFile::OnDataAvailable.md) et les autres notifications que vous souhaitez recevoir.  
  
#### Pour télécharger un fichier avec des monikers asynchrones  
  
1.  Déclarez une classe dérivée de [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md).  
  
2.  Substituez [OnDataAvailable](../Topic/CAsyncMonikerFile::OnDataAvailable.md) pour afficher les données.  
  
3.  Remplacez d'autres fonctions membres, y compris [OnProgress](../Topic/CAsyncMonikerFile::OnProgress.md), [OnStartBinding](../Topic/CAsyncMonikerFile::OnStartBinding.md), et [OnStopBinding](../Topic/CAsyncMonikerFile::OnStopBinding.md).  
  
4.  Déclarez une instance de la classe et utilisez\-la pour ouvrir des URL.  
  
 Pour plus d'informations sur le téléchargement asynchrone dans un contrôle ActiveX, consultez [Contrôles ActiveX Internet](../mfc/activex-controls-on-the-internet.md).  
  
## Voir aussi  
 [Tâches de programmation Internet MFC](../mfc/mfc-internet-programming-tasks.md)   
 [Éléments fondamentaux relatifs à la programmation Internet MFC](../mfc/mfc-internet-programming-basics.md)