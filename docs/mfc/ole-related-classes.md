---
title: "Classes liées à OLE | Documents Microsoft"
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
- ActiveX classes [MFC]
- OLE classes [MFC]
- OLE [MFC], classes
ms.assetid: 2135cf54-1d9d-4e0e-91b4-943b3440effa
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4cb40e237eb6197dfe7e0cf944f12d25ca0e28e4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ole-related-classes"></a>Classes liées à OLE
Ces classes fournissent un nombre de services différents, allant des exceptions dans le fichier d’entrée et de sortie.  
  
 [COleObjectFactory](../mfc/reference/coleobjectfactory-class.md)  
 Permet de créer des éléments lorsqu’il est demandé à partir d’autres conteneurs. Cette classe sert de classe de base pour les types plus spécifiques des fabriques, y compris `COleTemplateServer`.  
  
 [Intermédiaire de COleMessageFilter](../mfc/reference/colemessagefilter-class.md)  
 Utilisé pour gérer l’accès concurrentiel avec OLE Lightweight distant procédure appelle (LRPC).  
  
 [COleStreamFile](../mfc/reference/colestreamfile-class.md)  
 Utilise le modèle COM `IStream` interface afin de fournir `CFile` accès aux fichiers composés. Cette classe (dérivée de `CFile`) permet la sérialisation MFC utiliser le stockage structuré OLE.  
  
 [CRectTracker](../mfc/reference/crecttracker-class.md)  
 Utilisée pour autoriser le déplacement, redimensionnement et réorientation d’éléments de la place.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../mfc/class-library-overview.md)

