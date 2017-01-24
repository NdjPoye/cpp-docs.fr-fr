---
title: "Activation (C++) | Microsoft Docs"
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
  - "activer des objets"
  - "activation (C++)"
  - "activation (C++), éléments OLE incorporés"
  - "documents, OLE"
  - "objets incorporés"
  - "activation sur place"
  - "activation sur place, éléments liés et incorporés"
  - "OLE (C++), activation"
  - "OLE (C++), modifier"
  - "OLE (C++), activation sur place"
  - "activation des OLE"
  - "OLE (éléments), édition visuelle"
  - "applications serveur OLE, activation"
  - "édition visuelle"
  - "édition visuelle, activation"
ms.assetid: ed8357d9-e487-4aaa-aa6b-2edc4de25dfa
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Activation (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique le rôle de l'activation de la modification sur place de OLE éléments.  Après qu'un utilisateur a incorporé OLE un élément dans un document conteneur, il peut être utilisé.  Pour ce faire, l'utilisateur sur l'élément, qui permet l'élément.  L'activité les plus fréquentes pour l'activation remplace.  De nombreuses OLE éléments et, une fois activés pour la modification, faites pour refléter les menus et les barres d'outils de la fenêtre frame actuel jusqu'à la modification ceux qui appartiennent à l'application serveur qui a créé l'élément.  Ce comportement, appelé l'activation sur place, permet à l'utilisateur de modifier un élément incorporé dans un document composite sans quitter la fenêtre de document conteneur.  
  
 Il est également possible de modifier de OLE éléments imbriqués dans une fenêtre distincte.  Cela se produit si le conteneur ou l'application serveur ne prend pas en charge l'activation sur place.  Dans ce cas, lorsque l'utilisateur sur un élément incorporé, l'application serveur s'affiche dans une fenêtre distincte et l'élément incorporé apparaît comme son propre document.  L'utilisateur modifie l'élément dans la fenêtre.  Lorsque la modification est terminé, l'utilisateur ferme l'application serveur et retourne à l'application conteneur.  
  
 Ou bien, l'utilisateur peut choisir la modification « ouverte » avec l'ordre des **\<object\> Open** dans le menu de **Modifier**.  Cela entraîne l'objet dans une fenêtre distincte.  
  
> [!NOTE]
>  Modifier des éléments imbriqués dans une fenêtre distincte est comportement standard de la version 1 OLE, et certaines applications OLE peuvent prendre en charge que ce style de la modification.  
  
 L'activation sur place promeut une approche document\- centrale pour documenter la conception.  L'utilisateur peut traiter un document composite comme une entité unique, vous travaillez sur sans basculer entre les applications.  Toutefois, l'activation sur place n'est utilisée que pour les éléments imbriqués, pas pour les éléments : elles doivent être modifiés dans une fenêtre distincte.  Cela est dû au fait qu'un élément lié est enregistré réellement dans un emplacement différent.  La modification d'un élément lié a lieu dans le contexte réel des données, c. \- à\-d., où les données sont stockées.  Modification d'un élément lié dans une fenêtre distincte rappelle à l'utilisateur que les données appartenant à un autre document.  
  
 MFC ne prend pas en charge l'activation sur place imbriquée.  Si vous créez une application conteneur\/serveur, et ces conteneurs\/serveur est incorporé dans un conteneur et activé sur place différents, il ne peut pas sur place vérification des objets incorporés à l'intérieur de est.  
  
 Ce qui arrive à un élément incorporé lorsque les doubles\-clics utilisateur il dépend des verbes définis pour l'élément.  Pour plus d'informations, consultez l'[Activation : Verbes](../mfc/activation-verbs.md).  
  
## Voir aussi  
 [OLE](../mfc/ole-in-mfc.md)   
 [Conteneurs](../mfc/containers.md)   
 [Serveurs](../mfc/servers.md)