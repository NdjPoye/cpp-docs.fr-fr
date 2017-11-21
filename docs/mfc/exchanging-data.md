---
title: "Échange de données | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- property sheets [MFC], data exchange
- exchanging data with property sheets [MFC]
- DDX (dialog data exchange) [MFC], property sheets
ms.assetid: 689f02d0-51a9-455b-8ffb-5b44f0aefa28
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: da94d04a2cddb416ca62a71dbfa232317d55e612
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="exchanging-data"></a>Échange des données
Comme avec la plupart des boîtes de dialogue, l’échange de données entre la feuille de propriétés et de l’application est une des fonctions plus importantes de la feuille de propriétés. Cet article décrit comment accomplir cette tâche.  
  
 Échanger des données avec une feuille de propriétés sont en fait une question d’échanger des données avec les pages de propriétés individuelles de la feuille de propriétés. La procédure pour échanger des données avec une page de propriétés est identique à celui de l’échange de données avec une boîte de dialogue depuis un [CPropertyPage](../mfc/reference/cpropertypage-class.md) objet est simplement spécialisé [CDialog](../mfc/reference/cdialog-class.md) objet. La procédure tire parti de boîte de dialogue données exchange (DDX) usine de l’infrastructure, qui échange des données entre les contrôles dans une boîte de dialogue et les variables membres de l’objet de boîte de dialogue.  
  
 La différence importante entre l’échange de données avec une feuille de propriétés et une boîte de dialogue normale est que la feuille de propriétés comporte plusieurs pages, donc vous devez échanger des données avec toutes les pages de la feuille de propriétés. Pour plus d’informations sur DDX, consultez [échange de données de boîtes de dialogue et la Validation](../mfc/dialog-data-exchange-and-validation.md).  
  
 L’exemple suivant illustre l’échange de données entre une vue et deux pages d’une feuille de propriétés :  
  
 [!code-cpp[NVC_MFCDocView#4](../mfc/codesnippet/cpp/exchanging-data_1.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [Feuilles de propriétés](../mfc/property-sheets-mfc.md)

