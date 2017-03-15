---
title: "Tables des messages d&#233;riv&#233;es | Microsoft Docs"
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
  - "tables des messages dérivées"
  - "gestion des messages, gestionnaires de messages dérivés"
  - "tables des messages, dérivés"
  - "messages, router"
ms.assetid: 21829556-6e64-40c3-8279-fed85d99de77
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Tables des messages d&#233;riv&#233;es
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lors de la gestion des messages, l'activation de la table des messages d'une classe ne correspond pas à la fin de l'histoire de table des messages.  Que se passe\-t\-il si la classe `CMyView` \(dérivée de `CView`\) ne possède pas d'entrée correspondant à un message ?  
  
 N'oubliez pas que `CView`, la classe de base de `CMyView`, est dérivée elle\-même de `CWnd`.  Par conséquent `CMyView` *est*`CView` et *est*`CWnd`.  Chacune de ces classes possède sa propre table des messages.  L'illustration « une hiérarchie de vues » ci\-dessous montre la relation hiérarchique des classes, mais gardez à l'esprit qu'un objet `CMyView` est un objet qui a les caractéristiques des trois classes.  
  
 ![Hiérarchie d'un affichage](../mfc/media/vc38621.png "vc38621")  
Hiérarchie de vues  
  
 Si un message ne peut pas être mis en correspondance dans la table des messages de la classe `CMyView`, l'infrastructure recherche également la table des messages de la classe de base immédiate.  La macro `BEGIN_MESSAGE_MAP` au début de la table des messages spécifie deux noms de classes en tant qu'arguments :  
  
 [!code-cpp[NVC_MFCMessageHandling#2](../mfc/codesnippet/CPP/derived-message-maps_1.cpp)]  
  
 Le premier argument nomme la classe à laquelle la table des messages appartient.  Le deuxième argument fournit une connexion avec la classe de base immédiate \(`CView` ici\) afin que le framework puisse chercher dans la table des messages aussi.  
  
 Les gestionnaires de messages fournis dans une classe de base sont ainsi hérités par la classe dérivée.  Cela est très similaire aux fonctions membres virtuelles régulières sans avoir à rendre toutes les fonctions membre du gestionnaire virtuelles.  
  
 Si aucun responsable ne se trouve dans les tables des messages à l'exception de classe de base, le traitement par défaut du message est effectué.  Si le message est une commande, le framework le route vers la commande cible suivante.  Si c'est un message standard Windows, le message est transmis à la procédure d'affichage par défaut appropriée.  
  
 Pour accélérer la correspondance de la table des messages, le framework met en cache les correspondances récentes sur la probabilité de recevoir à nouveau le même message.  Une conséquence de cela est que le framework traite les messages non pris en charge assez efficacement.  Les tables des messages sont également plus spatialement efficaces que les implémentations qui utilisent des fonctions virtuelles.  
  
## Voir aussi  
 [Comment le Framework effectue des recherches dans les tables des messages](../mfc/how-the-framework-searches-message-maps.md)