---
title: "Fonctionnalités d’enregistrement affichage de Classes (MFC Data Access) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- record views, classes
- record view classes
ms.assetid: e7b2820f-09c4-483f-83c0-317e8be42bdf
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1c975aac0459a13a3fb95fdec3dff1a648b0efec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="features-of-record-view-classes--mfc-data-access"></a>Fonctionnalités des classes d'affichage des enregistrements (Accès aux données MFC)
Vous pouvez effectuer la programmation d’accès aux données de formulaire à la classe [CFormView](../mfc/reference/cformview-class.md), mais [CRecordView](../mfc/reference/crecordview-class.md) est généralement une meilleure classe dériver. En plus de son `CFormView` fonctionnalités, `CRecordView`:  
  
-   Fournit l’échange de données de boîtes de dialogue (DDX) entre les contrôles du formulaire et l’objet recordset associé.  
  
-   Gère les commandes Move First, Move Next, Move Previous et Move Last pour parcourir les enregistrements dans l’objet recordset associé.  
  
-   Mises à jour devient l’enregistrement actif lorsque l’utilisateur se déplace vers un autre enregistrement.  
  
 Pour plus d’informations sur la navigation, consultez [vues des enregistrements : prise en charge la Navigation dans une vue d’enregistrement](../data/supporting-navigation-in-a-record-view-mfc-data-access.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Vues des enregistrements (MFC Data Access)](../data/record-views-mfc-data-access.md)   
 [Liste de pilotes ODBC](../data/odbc/odbc-driver-list.md)