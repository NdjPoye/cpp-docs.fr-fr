---
title: "Serveurs&#160;: &#233;l&#233;ments du serveur | Microsoft Docs"
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
  - "architecture (C++), server-item"
  - "applications serveur OLE, éléments du serveur"
  - "éléments du serveur"
  - "éléments du serveur, implémenter"
  - "serveurs (C++), éléments du serveur"
ms.assetid: 28ba81a1-726a-4728-a52d-68bc7efd5a3c
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Serveurs&#160;: &#233;l&#233;ments du serveur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsqu'un conteneur lance un serveur afin qu'un utilisateur puisse modifier un élément OLE incorporé ou lié, l'application serveur « crée un élément du serveur. » L'élément du serveur, qui est un objet d'une classe dérivé d' `COleServerItem`, fournit une interface entre le document serveur et l'application conteneur.  
  
 La classe d' `COleServerItem` définit plusieurs fonctions membres substituables appelées par OLE, généralement en réponse aux requêtes du conteneur.  Les éléments du serveur peuvent représenter une partie du document serveur ou le document entier.  Lorsqu'un élément d'OLE est incorporé dans le document conteneur, l'élément du serveur représente le document serveur tout entier.  Lorsque l'élément OLE est lié, l'élément du serveur peut représenter une partie du document serveur ou le document entier, selon que la liaison est faite vers une partie ou vers le tout.  
  
 Dans l'exemple de [HIERSVR](../top/visual-cpp-samples.md), par exemple, la classe de l'élément serveur, **CServerItem**, a un membre qui est un pointeur vers un objet de la classe **CServerNode**.  L'objet de **CServerNode** est un nœud dans le document de l'application de HIERSVR, qui est une arborescence.  Lorsque l'objet de **CServerNode** est le nœud racine, l'objet de **CServerItem** représente le document entier.  Lorsque l'objet de **CServerNode** est un nœud enfant, l'objet de **CServerItem** représente une partie du document.  Pour obtenir un exemple de cette interaction, consultez l'exemple [HIERSVR](../top/visual-cpp-samples.md) du OLE de MFC.  
  
##  <a name="_core_implementing_server_items"></a> Implémenter des éléments du serveur  
 Si vous utilisez l'assisant d'application pour générer le code « démarreur » pour votre application, tout ce que vous devez effectuer pour inclure les éléments du serveur dans votre code de démarrage est de choisir l'une des options de serveur à partir de la page d'options d'OLE.  Si vous ajoutez des éléments du serveur à une application existante, procédez comme suit :  
  
#### Pour implémenter un élément du serveur  
  
1.  Dériver une classe de `COleServerItem`.  
  
2.  Dans votre classe dérivée, substituez la fonction membre d' `OnDraw`.  
  
     L'infrastructure appelle `OnDraw` pour afficher l'élément OLE dans un métafichier.  L'application conteneur utilise ce métafichier pour afficher l'élément.  La classe d'affichage de votre application a également une fonction membre d' `OnDraw`, utilisée pour afficher l'élément lorsque l'application serveur est active.  
  
3.  Implémenter une substitution de `OnGetEmbeddedItem` pour votre classe de document serveur.  Pour plus d'informations, consultez l'article [Serveurs : Implémenter des documents de serveur](../mfc/servers-implementing-server-documents.md) et l'exemple du OLE de MFC [HIERSVR](../top/visual-cpp-samples.md).  
  
4.  Implémentez la fonction membre d' `OnGetExtent` de la classe du serveur.  L'infrastructure appelle cette fonction pour extraire la taille de l'élément.  L'implémentation par défaut n'exécute aucune opération.  
  
##  <a name="_core_a_tip_for_server.2d.item_architecture"></a> Un indicateur pour l'architecture de l'élément serveur  
 Comme mentionné dans [Implémenter des éléments du serveur](#_core_implementing_server_items), les applications serveur doivent pouvoir afficher les éléments à la fois dans la vue du serveur et dans un métafichier utilisé par l'application conteneur.  Dans l'architecture de l'application de la bibliothèque Microsoft Foundation Class, la fonction membre d' `OnDraw` de la classe d'affichage affiche l'élément lorsqu'elle est modifiée \(consultez [CView::OnDraw](../Topic/CView::OnDraw.md) dans *la référence de la bibliothèque de classes*\).  `OnDraw` de l'élément du serveur affiche l'élément dans un métafichier dans tous les autres cas \(consultez [COleServerItem::OnDraw](../Topic/COleServerItem::OnDraw.md)\).  
  
 Vous pouvez éviter la duplication de code en écrivant des fonctions d'assistance dans la classe du document serveur et en les appelant à partir des fonctions d' `OnDraw` dans vos classes d'affichage et d'éléments du serveur.  L'exemple de liaison et incorporation d'objets MFC [HIERSVR](../top/visual-cpp-samples.md) utilise cette stratégie: les fonctions **CServerView::OnDraw** et **CServerItem::OnDraw** appellent toutes deux **CServerDoc::DrawTree** pour afficher l'élément.  
  
 La vue et l'élément ont tous deux des fonctions membres d' `OnDraw` car elles dessinent dans différentes conditions.  L'affichage doit prendre en compte des facteurs tels que le zoom, la taille et l'extension de sélection, la réduction, et des éléments d'interface utilisateur tels que les barres de défilement.  L'élément du serveur, en revanche, dessine toujours l'objet OLE entier.  
  
 Pour plus d'informations, consultez [CView::OnDraw](../Topic/CView::OnDraw.md), [COleServerItem](../mfc/reference/coleserveritem-class.md), [COleServerItem::OnDraw](../Topic/COleServerItem::OnDraw.md), et l' [COleServerDoc::OnGetEmbeddedItem](../Topic/COleServerDoc::OnGetEmbeddedItem.md) dans *la référence de la bibliothèque de classes*.  
  
## Voir aussi  
 [Serveurs](../mfc/servers.md)