---
title: "Gestion des commandes dans le document | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "WM_COMMAND"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gestion des commandes"
  - "gestion des commandes, commandes dans les documents"
  - "documents, gérer des messages dans"
  - "documents, tables des messages"
  - "gestion des messages, WM_COMMAND (messages)"
  - "tables des messages, dans la classe de document"
  - "WM_COMMAND"
ms.assetid: c7375584-27af-4275-b2fd-afea476785d0
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Gestion des commandes dans le document
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Votre classe de document peut aussi gérer des commandes générées par les éléments de menu, des boutons de la barre d'outils, ou des touches accélérateur.  Par défaut, **CDocument** gère la sauvegarde et la sauvegarde sous comme commandes du menu Fichier, en utilisant la sérialisation.  D'autres commandes qui affectent les données peuvent également être gérées par les fonctions membres de votre document.  Par exemple, dans le programme de dessin à main levée, la classe `CScribDoc` permet de gérer la commande Edit Clear All, qui supprime toutes les données actuellement stockées dans le document.  Les documents peuvent avoir des tables de messages, mais contrairement aux vues, les documents ne peuvent pas traiter les messages standard windows — uniquement les messages **WM\_COMMAND**, ou « commandes. »  
  
## Voir aussi  
 [Utilisation de documents](../mfc/using-documents.md)