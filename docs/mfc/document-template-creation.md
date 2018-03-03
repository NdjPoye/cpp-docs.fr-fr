---
title: "Création d’un modèle de document | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- document templates [MFC]
- constructors [MFC], document template
- document templates [MFC], creating
- MFC, document templates
- templates [MFC], document templates
ms.assetid: c87f1821-7cbf-442e-9690-f126ae7fb783
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 04950601a74b1ed3e44b236e1d07dcdff997eca6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="document-template-creation"></a>Création de modèle de document
Lors de la création d’un nouveau document en réponse à une `New` ou **ouvrir** commande à partir de la **fichier** menu, le modèle de document crée également une fenêtre frame dont vous souhaitez afficher le document.  
  
 Le constructeur de modèle de document spécifie les types de documents, windows et le modèle sera en mesure de créer des vues. Cela est déterminé par les arguments que vous passez au constructeur de modèle de document. Le code suivant illustre la création d’un [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md) pour un exemple d’application :  
  
 [!code-cpp[NVC_MFCDocView#7](../mfc/codesnippet/cpp/document-template-creation_1.cpp)]  
  
 Le pointeur vers une nouvelle `CMultiDocTemplate` objet est utilisé en tant qu’argument à [AddDocTemplate](../mfc/reference/cwinapp-class.md#adddoctemplate). Arguments pour le `CMultiDocTemplate` constructeur incluent l’ID de ressource associé aux menus et les accélérateurs du type de document, et trois utilisations de la [RUNTIME_CLASS](../mfc/reference/run-time-object-model-services.md#runtime_class) (macro). `RUNTIME_CLASS`Retourne le [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) objet pour la classe C++ nommée comme argument. Les trois `CRuntimeClass` objets transmis au constructeur de modèle de document fournissent les informations nécessaires pour créer de nouveaux objets des classes spécifiées pendant le processus de création de document. L’exemple illustre la création d’un modèle de document crée `CScribDoc` avec des objets `CScribView` objets attachés. Les vues sont encadrées par des fenêtres frame enfants MDI standard.  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles de document et le processus de création de Document/Vue](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [La création de document/vue](../mfc/document-view-creation.md)   
 [Relations entre les objets MFC](../mfc/relationships-among-mfc-objects.md)   
 [Création de documents, fenêtres et vues](../mfc/creating-new-documents-windows-and-views.md)

