---
title: "Serveurs&#160;: impl&#233;mentations de fen&#234;tres frame sur place | Microsoft Docs"
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
  - "fenêtres frame, implémenter"
  - "fenêtres frame, sur place"
  - "sur place, fenêtres frame"
  - "applications serveur OLE, fenêtres frame"
  - "serveurs, sur place, fenêtres frame"
ms.assetid: 09bde4d8-15e2-4fba-8d14-9b954d926b92
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Serveurs&#160;: impl&#233;mentations de fen&#234;tres frame sur place
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique ce que vous devez effectuer pour implémenter des fenêtres cadres sur place dans votre application d'édition visuelle de serveur si vous n'utilisez pas l'Assistant d'application pour créer votre application serveur.  Au lieu de suivre la procédure soulignée dans cet article, vous pouvez utiliser une classe existante d'affichage de cadre de fenêtre soit depuis une application générée par l'Assistant soit depuis un échantillon fourni avec Visual C\+\+.  
  
#### Pour déclarer une classe de cadre de fenêtre sur place  
  
1.  Dérivez une classe de fenêtre cadre sur place depuis `COleIPFrameWnd`.  
  
    -   Utilisez la macro `DECLARE_DYNCREATE` dans votre fichier d'en\-tête de la classe.  
  
    -   Utilisez la macro `IMPLEMENT_DYNCREATE` dans votre fichier de l'implémentation de classe \(.cpp\).  Cela permet aux objets de cette classe d'être créés par le .NET Framework.  
  
2.  Déclarez un membre de `COleResizeBar` dans la classe cadre de fenêtre.  Cela est nécessaire si vous voulez prendre en charge le redimensionnement sur place dans les applications serveur.  
  
     Déclarez un gestionnaire de messages `OnCreate` \(à l'aide de la fenêtre **Propriétés** \), puis appelez **Créer** pour votre membre de `COleResizeBar`, si vous l'avez défini.  
  
3.  Si vous avez une barre d'outils, déclarez un membre de `CToolBar` dans la classe cadre de fenêtre.  
  
     Remplacer la fonction membre de `OnCreateControlBars` pour créer une barre d'outils lorsque le serveur est en place et actif.  Par exemple :  
  
     [!code-cpp[NVC_MFCOleServer#1](../mfc/codesnippet/CPP/servers-implementing-in-place-frame-windows_1.cpp)]  
  
     Consultez l'étude de ce code en suivant l'étape 5.  
  
4.  Incluez le fichier d'en\-tête pour cette classe d'affichage sur le champ dans le fichier .cpp principal.  
  
5.  Dans `InitInstance` pour votre classe d'application, appelez la fonction `SetServerInfo` de l'objet modèle de document pour spécifier les ressources et la fenêtre cadre sur place à utiliser pour l'ouverture et les modifications sur place.  
  
 La série d'appels de fonction dans l'instruction **if** crée la barre d'outils de ressources que le serveur a fournies.  À ce stade, la barre d'outils fait partie de la hiérarchie dans la fenêtre du conteneur.  Cette barre d'outils est dérivée de `CToolBar`, il passe les messages à son propriétaire, la fenêtre cadre de l'application conteneur, sauf si vous modifiez le propriétaire.  C'est pourquoi l'appel à `SetOwner` est nécessaire.  Cet appel modifie la fenêtre lorsque les commandes sont envoyées à la fenêtre cadre sur place du serveur, ce qui entraîne que des messages sont passés au serveur.  Cela permet au serveur de réagir à des opérations dans la barre d'outils qu'elle propose.  
  
 L'ID de la bitmap de la barre d'outils doit être le même que les autres ressources sur place définies dans votre application serveur.  Voir le [Menus et ressources : Ajouts de serveur](../mfc/menus-and-resources-server-additions.md) pour plus d'informations.  
  
 Pour plus d'informations, consultez [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md), [COleResizeBar](../mfc/reference/coleresizebar-class.md), et le [CDocTemplate::SetServerInfo](../Topic/CDocTemplate::SetServerInfo.md) dans *la référence de la bibliothèque de classes*.  
  
## Voir aussi  
 [Serveurs](../mfc/servers.md)   
 [Serveurs : implémentation d'un serveur](../mfc/servers-implementing-a-server.md)   
 [Serveurs : implémentation de documents de serveur](../mfc/servers-implementing-server-documents.md)   
 [Serveurs : éléments du serveur](../mfc/servers-server-items.md)