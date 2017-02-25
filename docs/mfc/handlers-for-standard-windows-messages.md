---
title: "Gestionnaires pour les messages Windows standard | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "afx_msg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fonctions (C++), gestionnaire"
  - "fonctions gestionnaires, messages Windows standard"
  - "gestion des messages (C++), gestionnaires de messages Windows"
  - "messages (C++), Windows"
  - "messages Windows (C++), gestionnaires"
ms.assetid: 19412a8b-2c38-4502-81da-13c823c7e36c
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Gestionnaires pour les messages Windows standard
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les gestionnaires par défaut pour les messages Windows standard \(**WM\_**\) sont prédéfinis dans la classe `CWnd`.  La bibliothèque de classes base des noms de ces gestionnaires sur le nom du message.  Par exemple, le gestionnaire du message `WM_PAINT` est déclaré dans `CWnd` comme suit :  
  
 `afx_msg void OnPaint();`  
  
 Le mot clé **afx\_msg** suggère l'effet du mot clé C\+\+ **virtual** en caractéristisant les gestionnaires d'autres fonctions membres `CWnd`.  Notez, toutefois, que ces fonctions ne sont pas réellement virtuelles ; elles sont plutôt implémentées dans les tables des messages.  Les tables des messages dépendent uniquement les macros standard du préprocesseur, et non des extensions au langage C\+\+.  Le mot clé **afx\_msg** correspond à un espace blanc après prétraitement.  
  
 Pour remplacer un gestionnaire défini dans une classe de base, il vous suffit de définir une fonction du même prototype de votre classe dérivée et créer une entrée dans la table des messages du gestionnaire.  Le gestionnaire « substitue » tout gestionnaire du même nom dans n'importe laquelle des classes de base de vos classes.  
  
 Dans certains cas, le gestionnaire doit appeler le gestionnaire de remplacement dans la classe de base pour que la classe de base et Windows puissent traiter le message.  L'emplacement où vous appelez le gestionnaire de classe de base dans votre fichier dépend des cas.  Parfois vous devez appeler le gestionnaire de classe de base en premier et parfois en dernier.  Parfois vous appelez le gestionnaire de classe de base de manière conditionnelle, si vous choisissez de ne pas traiter le message vous\-même.  Parfois vous devez appeler le gestionnaire de classe de base, puis exécuter de manière conditionnelle votre propre code manager, selon la valeur et l'état retourné par le gestionnaire de la classe de base.  
  
> [!CAUTION]
>  Il n'est pas sécurisé de modifier les arguments passés dans un gestionnaire si vous envisagez de les transmettre à un gestionnaire de la classe de base.  Par exemple, vous pouvez être tenté de modifier l'argument `nChar` du gestionnaire `OnChar` \(pour convertir en majuscules, par exemple\).  Ce comportement est suffisamment obscur, mais si vous devez obtenir cet effet, utilisez la fonction membre **SendMessage** `CWnd` à la place.  
  
 Comment déterminer la méthode appropriée pour remplacer un message donné ?  Lorsque la fenêtre Propriétés dans la structure de la fonction gestionnaire d'un message donné \(un gestionnaire `OnCreate` pour `WM_CREATE`, par exemple\) cela prend la forme de la fonction membre substituée recommandée.  L'exemple suivant recommande que le gestionnaire appelle d'abord le gestionnaire de classe de base et procède uniquement à la condition qu'il ne retourne pas – 1.  
  
 [!code-cpp[NVC_MFCMessageHandling#3](../mfc/codesnippet/CPP/handlers-for-standard-windows-messages_1.cpp)]  
  
 Par convention, les noms de ces gestionnaires commencent par le préfixe « On ». Certains de ces gestionnaires n'occupent aucun argument, tandis que d'autres en ont plusieurs.  Certains ont également un type de retour autre que `void`.  Les gestionnaires par défaut pour tous les messages de **WM\_** sont décrits dans *le guide de MFC* comme fonctions membres de la classe `CWnd` dont les noms commencent par « On ». Les déclarations de fonctions membres dans `CWnd` portent le préfixe **afx\_msg**.  
  
## Voir aussi  
 [Déclaration des fonctions de gestionnaire de messages](../mfc/declaring-message-handler-functions.md)