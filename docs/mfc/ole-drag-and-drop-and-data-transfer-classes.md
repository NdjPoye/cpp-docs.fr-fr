---
title: "OLE glisser-déplacer et transfert de données Classes | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.ole
dev_langs:
- C++
helpviewer_keywords:
- ActiveX classes [MFC]
- OLE drag and drop [MFC], and data transfer classes
- drag and drop [MFC], classes
- data transfer [MFC], OLE
- data transfer classes [MFC]
ms.assetid: c8ab2825-ed69-4b88-8ae6-f368b94726b8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0e8c5a54184bcf6450bf39b39a6b90d7865c09d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ole-drag-and-drop-and-data-transfer-classes"></a>Classes de glisser-déposer OLE et de transfert de données
Ces classes sont utilisées dans les transferts de données OLE. Ils permettent aux données à transférer entre des applications à l’aide du Presse-papiers ou par glisser-déplacer.  
  
 [COleDropSource](../mfc/reference/coledropsource-class.md)  
 Contrôle de l’opération de glisser-déplacer à partir du début à la fin. Cette classe détermine l’heure de début de l’opération de glissement et lorsqu’elle se termine. Elle affiche également le curseur lors de l’opération de glisser-déplacer.  
  
 [COleDataSource](../mfc/reference/coledatasource-class.md)  
 Utilisé lorsqu’une application fournit des données pour un transfert de données. `COleDataSource`peut être considéré comme un objet du Presse-papiers et orienté objet.  
  
 [COleDropTarget](../mfc/reference/coledroptarget-class.md)  
 Représente la cible d’une opération de glisser-déplacer. A `COleDropTarget` objet correspond à une fenêtre. Elle détermine s’il faut accepter toutes les données déposés sur lui et implémentant l’opération de suppression réelle.  
  
 [COleDataObject](../mfc/reference/coledataobject-class.md)  
 Utilisé en tant que le côté récepteur à `COleDataSource`. `COleDataObject`objets fournissent l’accès aux données stockées par une `COleDataSource` objet.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../mfc/class-library-overview.md)

