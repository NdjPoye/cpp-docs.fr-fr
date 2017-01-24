---
title: "Comment&#160;: utiliser la r&#233;f&#233;rence crois&#233;e de la table des messages | Microsoft Docs"
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
  - "vc.mfc.messages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fenêtres (C++), tables des messages"
ms.assetid: 2e863d23-9e58-45ba-b5e4-a8ceefccd0c8
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: utiliser la r&#233;f&#233;rence crois&#233;e de la table des messages
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dans les entrées étiquetées \<memberFxn\>, entrez votre propre fonction membre d'une classe dérivée de [CWnd](../../mfc/reference/cwnd-class.md).  Attribuez à votre fonction le nom que vous souhaitez.  D'autres fonctions, telles que `OnActivate`, sont des fonctions membres de la classe `CWnd`.  Si appelé, ils passent le message à la fonction Windows de `DefWindowProc`.  Pour traiter les messages de notification Windows, substituez la fonction correspondante de `CWnd` dans la classe dérivée.  Votre fonction doit appeler la fonction remplacée dans votre classe de base pour permettre à la classe de base et à Windows de répondre au message.  
  
 Dans tous les cas, placez le prototype de la fonction dans `CWnd`\- en\-tête dérivée de la classe, et codez l'entrée de la table des messages comme indiqué.  
  
 Les termes suivants sont utilisés:  
  
|Terme|Définition|  
|-----------|----------------|  
|id|N'importe quel ID d'élément de menu défini par l'utilisateur \(messages de**WM\_COMMAND** \) ou ID de contrôle \(messages de notification de la fenêtre enfant\).|  
|« message » et « wNotifyCode »|ID de message Windows comme défini dans WINDOWS.H.|  
|nMessageVariable|Nom d'une variable qui contient la valeur de retour de la fonction Windows de **RegisterWindowMessage**.|  
  
## Voir aussi  
 [Tables des messages](../../mfc/reference/message-maps-mfc.md)