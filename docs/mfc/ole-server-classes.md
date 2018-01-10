---
title: Classes de serveur OLE | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.ole
dev_langs: C++
helpviewer_keywords:
- OLE server applications [MFC], server classes
- OLE server documents
- COM components, classes [MFC]
- component classes [MFC]
ms.assetid: 8e9b67a2-c0ff-479c-a8d6-19b36c5e6fc6
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d23c7cb23d9221f8f2183c666a99c70ef149db3e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ole-server-classes"></a>Classes de serveur OLE
Ces classes sont utilisées par les applications serveur. Documents de serveur sont dérivés de `COleServerDoc` plutôt qu’à partir **CDocument**. Notez que puisque `COleServerDoc` est dérivée de `COleLinkingDoc`, documents de serveur peuvent également être des conteneurs qui prennent en charge la liaison.  
  
 La `COleServerItem` classe représente un document ou une partie d’un document qui peut être incorporé dans un autre document ou lié.  
  
 `COleIPFrameWnd`et `COleResizeBar` prennent en charge la modification sur place alors que l’objet est dans un conteneur, et `COleTemplateServer` prend en charge la création de paires de document/vue objets OLE à partir d’autres applications peuvent être modifiés.  
  
 [COleServerDoc](../mfc/reference/coleserverdoc-class.md)  
 Utilisé comme classe de base pour les classes de documents de l’application serveur. `COleServerDoc`objets fournissent l’essentiel de la prise en charge de serveur via les interactions avec `COleServerItem` objets. Capacité d’édition Visual est fournie à l’aide de l’architecture document/vue de la bibliothèque de classes.  
  
 [CDocItem](../mfc/reference/cdocitem-class.md)  
 De classe de base abstraite `COleClientItem` et `COleServerItem`. Les objets des classes dérivées de `CDocItem` représentent les parties de documents.  
  
 [COleServerItem](../mfc/reference/coleserveritem-class.md)  
 Utilisé pour représenter l’interface OLE `COleServerDoc` éléments. Il existe généralement une `COleServerDoc` objet qui représente la partie intégrante d’un document. Dans les serveurs qui prennent en charge des liens vers les parties de documents, il peut y avoir plusieurs `COleServerItem` objets, chacun d’eux représente un lien vers une partie du document.  
  
 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)  
 Fournit la fenêtre frame pour une vue lorsqu’un document serveur est en cours de modification en place.  
  
 [COleResizeBar](../mfc/reference/coleresizebar-class.md)  
 Fournit l’interface utilisateur standard pour le redimensionnement en place. Objets de cette classe sont toujours utilisés conjointement avec `COleIPFrameWnd` objets.  
  
 [COleTemplateServer](../mfc/reference/coletemplateserver-class.md)  
 Utilisé pour créer des documents à l’aide de l’architecture document/vue de l’infrastructure. A `COleTemplateServer` objet délègue la majeure partie de son travail associé à un `CDocTemplate` objet.  
  
 [COleException](../mfc/reference/coleexception-class.md)  
 Une exception résultant d’une défaillance lors du traitement de OLE. Cette classe est utilisée par les conteneurs et les serveurs.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../mfc/class-library-overview.md)
