---
title: "Création de document / vue | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- documents [MFC], creating
- views [MFC], and frame windows
- views [MFC], creating
- tables [MFC]
- MFC, views
- document/view architecture [MFC], creating document/view
- object creators
- MFC, documents
- tables [MFC], objects each MFC object creates
ms.assetid: bda14f41-ed50-439d-af9e-591174e7dd64
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c6997189f23ea7599dde0a1b19ba9f0ea350378d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="documentview-creation"></a>Création d'un document/d'une vue
Le framework fournit des implémentations de la `New` et **ouvrir** commandes (entre autres) sur le **fichier** menu. Création d’un nouveau document et sa vue associée et la fenêtre frame est un effort conjoint de l’objet d’application, un modèle de document, du document nouvellement créé et la fenêtre frame nouvellement créé. Le tableau suivant récapitule les objets créent que.  
  
### <a name="object-creators"></a>Créateurs d’objets  
  
|créateur|Crée|  
|-------------|-------------|  
|Objet Application|Modèle de document|  
|Modèle de document|Document|  
|Modèle de document|Fenêtre frame|  
|Fenêtre frame|Vue|  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles de document et le processus de création de Document/Vue](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [Création de modèle de document](../mfc/document-template-creation.md)   
 [Relations entre les objets MFC](../mfc/relationships-among-mfc-objects.md)   
 [Création de documents, fenêtres et vues](../mfc/creating-new-documents-windows-and-views.md)

