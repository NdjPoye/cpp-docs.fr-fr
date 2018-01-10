---
title: "Serveurs : Implémentation d’un serveur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- servers, implementing
- OLE server applications [MFC], implementing OLE servers
ms.assetid: 5bd57e8e-3b23-4f23-9597-496fac2d24b5
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 148a3da3c904f5c314c75fb71deede3c92163cc6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="servers-implementing-a-server"></a>Serveurs : implémentation d'un serveur
Cet article explique le code que l’Assistant Application MFC crée pour une application serveur d’édition visuelle. Si vous n’utilisez pas l’Assistant application, cet article répertorie les domaines où vous devez écrire du code pour implémenter une application serveur.  
  
 Si vous utilisez l’Assistant application pour créer une nouvelle application serveur, il fournit une quantité importante de code spécifique au serveur pour vous. Si vous ajoutez une fonctionnalité serveur Édition visuelle à une application existante, vous devez dupliquer le code que l’Assistant application aurait fourni avant d’ajouter le reste du code serveur nécessaires.  
  
 Le code de serveur qui fournit de l’Assistant application se divise en plusieurs catégories :  
  
-   Définition des ressources serveur :  
  
    -   La ressource de menu utilisée lorsque le serveur modifie un élément incorporé dans sa propre fenêtre.  
  
    -   Les ressources de menu et barre d’outils utilisés lorsque le serveur est actif sur place.  
  
     Pour plus d’informations sur ces ressources, consultez [Menus et ressources : ajouts de serveur](../mfc/menus-and-resources-server-additions.md).  
  
-   Définition d’une classe d’élément dérivé `COleServerItem`. Pour plus d’informations sur les éléments de serveur, consultez [serveurs : éléments du serveur](../mfc/servers-server-items.md).  
  
-   Modification de la classe de base de la classe de document à `COleServerDoc`. Pour plus d’informations, consultez [serveurs : implémentation des Documents serveur](../mfc/servers-implementing-server-documents.md).  
  
-   Définition d’une classe de fenêtre frame dérivée de `COleIPFrameWnd`. Pour plus d’informations, consultez [serveurs : implémentation des fenêtres de Frame sur Place](../mfc/servers-implementing-in-place-frame-windows.md).  
  
-   Création d’une entrée pour l’application serveur dans la base de données d’inscription Windows et l’inscription de la nouvelle instance du serveur avec le système OLE. Pour plus d’informations sur ce sujet, consultez [inscription](../mfc/registration.md).  
  
-   Initialisation et lancement de l’application serveur. Pour plus d’informations sur ce sujet, consultez [inscription](../mfc/registration.md).  
  
 Pour plus d’informations, consultez [COleServerItem](../mfc/reference/coleserveritem-class.md), [COleServerDoc](../mfc/reference/coleserverdoc-class.md), et [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md) dans les *Class Library Reference*.  
  
## <a name="see-also"></a>Voir aussi  
 [Serveurs](../mfc/servers.md)   
 [Conteneurs](../mfc/containers.md)   
 [Menus et ressources (OLE)](../mfc/menus-and-resources-ole.md)   
 [Inscription](../mfc/registration.md)

