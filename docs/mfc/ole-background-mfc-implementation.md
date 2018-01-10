---
title: "Arrière-plan OLE : Implémentation MFC | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IMarshall
- IMoniker
dev_langs: C++
helpviewer_keywords:
- MFC libraries, implementing
- OLE MFC library implementation
- OLE IMarshal interface
- IMoniker interface, MFC
- IMarshall class [MFC]
- OLE, compound files
- OLE IMoniker interface
- OLE IUnknown
ms.assetid: 2b67016a-d78e-4d60-925f-c28ec8fb6180
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 530cc14135fd38e2177e00dc87974e96ffe24b6c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ole-background-mfc-implementation"></a>Arrière-plan OLE : implémentation MFC
En raison de la taille et de la complexité de l'API OLE brute, l'appeler directement pour écrire des applications OLE peut prendre beaucoup de temps. L'objectif de l'implémentation de la bibliothèque MFC OLE est de réduire la charge de travail dans l'écriture des applications complètes et de type OLE.  
  
 Cet article explique les parties de l'API OLE qui n'ont pas été implémentées dans MFC. La discussion explique également comment ce qui est implémenté mappe à la section OLE du Kit de développement Windows.  
  
##  <a name="_core_portions_of_ole_not_implemented_by_the_class_library"></a>Parties OLE non implémentées par la bibliothèque de classes  
 Certaines fonctionnalités et interfaces OLE ne sont pas directement fournies par MFC. Si vous souhaitez utiliser ces fonctionnalités, vous pouvez appeler l'API OLE directement.  
  
 Interface IMoniker  
 L'interface `IMoniker` est implémentée par la bibliothèque de classes (par exemple, la classe `COleServerItem`) mais n'a pas été exposée précédemment au programmeur. Pour plus d’informations sur cette interface, consultez les implémentations du Moniker OLE dans la section OLE du Kit de développement Windows. Toutefois, consultez également la classe [CMonikerFile](../mfc/reference/cmonikerfile-class.md) et [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md).  
  
 Interfaces IUnknown et IMarshal  
 Le **IUnknown** interface est implémentée par la bibliothèque de classes mais n’est pas exposée au programmeur. Le **IMarshal** interface n’est pas implémentée par la bibliothèque de classes mais est utilisée en interne. Les serveurs d’automation générés à l’aide de la bibliothèque de classes incorporent déjà des fonctions de marshaling.  
  
 Docfiles (fichiers composés)  
 Les fichiers composés sont partiellement pris en charge par la bibliothèque de classes. Aucune des fonctions qui manipulent directement les fichiers composés au delà de la création n'est prise en charge. MFC utilise la classe **COleFileStream** pour prendre en charge la manipulation des flux avec des fonctions de fichier standard. Pour plus d’informations, consultez l’article [conteneurs : fichiers composés](../mfc/containers-compound-files.md).  
  
 Serveurs intra-processus et gestionnaires d'objets  
 Les serveurs intra-processus et les gestionnaires d'objets permettent l'implémentation des données de modification visuelle ou des objets COM (Component Object Model) complets dans une bibliothèque de liens dynamiques (DLL). Pour cela, vous pouvez implémenter la DLL en appelant l'API OLE directement. Toutefois, si vous disposez d'un accès en écriture à un serveur Automation et que celui-ci n'offre pas d'interface utilisateur, vous pouvez utiliser AppWizard pour faire de votre serveur un serveur intra-processus et l'intégrer complètement dans une DLL. Pour plus d’informations sur ces sujets, consultez [serveurs Automation](../mfc/automation-servers.md).  
  
> [!TIP]
>  La façon la plus simple d'implémenter un serveur Automation est de le placer dans une DLL. MFC prend en charge cette méthode.  
  
 Pour plus d’informations sur la façon dont les classes Microsoft Foundation OLE implémentent les interfaces OLE, consultez les Notes techniques MFC [38](../mfc/tn038-mfc-ole-iunknown-implementation.md), [39](../mfc/tn039-mfc-ole-automation-implementation.md), et [40](../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Arrière-plan OLE](../mfc/ole-background.md)   
 [Arrière-plan OLE : stratégies d’implémentation](../mfc/ole-background-implementation-strategies.md)

