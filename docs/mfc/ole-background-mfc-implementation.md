---
title: "Arri&#232;re-plan OLE&#160;: impl&#233;mentation MFC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IMarshall"
  - "IMoniker"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IMarshall (classe)"
  - "IMoniker (interface), MFC"
  - "bibliothèques MFC, implémenter"
  - "OLE IMarshal (interface)"
  - "OLE IMoniker (interface)"
  - "OLE IUnknown"
  - "OLE (implémentation de bibliothèque MFC)"
  - "OLE, fichiers composés"
ms.assetid: 2b67016a-d78e-4d60-925f-c28ec8fb6180
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Arri&#232;re-plan OLE&#160;: impl&#233;mentation MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

En raison de la taille et de la complexité de l'API OLE brute, l'appeler directement pour écrire des applications OLE peut être très coûteux en temps.  L'objectif de l'implémentation de la bibliothèque MFC OLE est de réduire la quantité de travail à effectuer pour écrire des applications complètes et capables d'OLE.  
  
 Cet article explique les parties de l'API OLE qui n'ont pas été implémentés dans MFC.  La discussion explique également comment ce qui est implémenté mappe à la section d'OLE [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
##  <a name="_core_portions_of_ole_not_implemented_by_the_class_library"></a> Portions d'OLE non implémentées par la bibliothèque de classes  
 Certaines fonctionnalités et interfaces d'OLE ne sont pas directement fournies par MFC.  Si vous souhaitez utiliser ces fonctionnalités, vous pouvez appeler l'API OLE directement.  
  
 Interface IMoniker  
 L'interface de `IMoniker` est implémentée par la bibliothèque de classes \(par exemple, la classe d' `COleServerItem` \) mais n'a pas été exposée précédemment au programmeur.  Pour plus d'informations sur cette interface, consultez Implémentations d'OLE Moniker dans la section d'OLE de [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  Toutefois, consultez également la classe [CMonikerFile](../mfc/reference/cmonikerfile-class.md) et [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md).  
  
 Interfaces de IUnknown et d'IMarshal  
 L'interface de **IUnknown** est implémentée par la bibliothèque de classes mais n'est pas exposée au programmeur.  L'interface de **IMarshal** n'est pas implémentée par la bibliothèque de classes mais est utilisée en interne.  Les serveurs d'automation générés à l'aide de la bibliothèque de classes incorporent déjà des fonctions de marshaling.  
  
 Docfiles \(fichiers composés\)  
 Les fichiers composites sont partiellement pris en charge par la bibliothèque de classes.  Aucune des fonctions qui manipulent directement les fichiers composites au delà de la création n'est prise en charge.  MFC utilise la classe **COleFileStream** pour prendre en charge la manipulation de flux de fonctions de fichiers standard.  Pour plus d'informations, consultez l'article [Conteneurs : Fichiers composites](../mfc/containers-compound-files.md).  
  
 Serveurs in\-process et gestionnaires d'objets  
 Les serveurs in\-process et les gestionnaires d'objets permettent l'implémentation des données de modification visuelle ou des modèles d'objets de composants \(COM\) dans une bibliothèque de liens dynamiques \(DLL\).  Pour cela, vous pouvez implémenter la DLL en appelant les API OLE directement.  Toutefois, si vous écrivez un serveur Automation et que celui\-ci ne dispose pas d'une interface utilisateur, vous pouvez utiliser un assistant d'application pour faire de votre serveur un serveur in\-process et l'intégrer complètement dans une DLL.  Pour plus d'informations sur ces thèmes, consultez [Serveurs d'Automation](../mfc/automation-servers.md).  
  
> [!TIP]
>  La façon la plus simple d'implémenter un serveur d'Automation est de le placer dans une DLL.  MFC prend en charge cette méthode.  
  
 Pour plus d'informations sur la façon dont les classes OLE de Microsoft Foundation implémentent des interfaces OLE, consultez la section notes techniques de MFC [38](../mfc/tn038-mfc-ole-iunknown-implementation.md), [39](../mfc/tn039-mfc-ole-automation-implementation.md), et [40](../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md).  
  
## Voir aussi  
 [Arrière\-plan OLE](../mfc/ole-background.md)   
 [Arrière\-plan OLE : stratégies d'implémentation](../mfc/ole-background-implementation-strategies.md)