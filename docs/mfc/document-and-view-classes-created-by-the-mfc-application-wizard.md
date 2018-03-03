---
title: "Documenter et affichage de Classes créées par l’Assistant Application MFC | Documents Microsoft"
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
- document classes [MFC]
- document classes [MFC], created by application wizards
- application wizards [MFC], document/view classes created
- view classes [MFC], created by application wizards
ms.assetid: 70c34a60-2701-4981-acea-c08a5787d8e6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7cddf8b72e9927a298cbd39d4f9790965e4b8f74
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="document-and-view-classes-created-by-the-mfc-application-wizard"></a>Classes de document et de vue créées par l'Assistant Application MFC
L’Assistant Application MFC vous donne un coup de développement de votre programme en créant des documents squelette et des classes d’affichage pour vous. Vous pouvez ensuite [mapper les commandes et les messages à ces classes](../mfc/reference/mapping-messages-to-functions.md) et utiliser l’éditeur de code source Visual C++ pour écrire leurs fonctions membres.  
  
 La classe de document créée par l’Assistant Application MFC est dérivée de la classe [CDocument](../mfc/reference/cdocument-class.md). La classe d’affichage est dérivée [CView](../mfc/reference/cview-class.md). Les noms que l’Assistant Application attribue à ces classes et les fichiers qui contiennent les sont basées sur le nom du projet que vous indiquez dans la boîte de dialogue Assistant Création d’applications. Dans l’Assistant Application, vous pouvez utiliser la page Classes générées pour modifier les noms par défaut.  
  
 Certaines applications sont peut-être plus d’une classe de document, classe d’affichage ou classe de fenêtre frame. Pour plus d’informations, consultez [plusieurs Types de documents, vues et fenêtres Frame](../mfc/multiple-document-types-views-and-frame-windows.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Architecture document/vue](../mfc/document-view-architecture.md)

