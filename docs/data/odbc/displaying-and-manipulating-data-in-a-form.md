---
title: "Affichage et manipulation de données dans un formulaire | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- forms [C++], displaying data
- displaying data [C++], forms
- ODBC [C++], forms
- record views [C++], displaying data
- data [MFC]
- data [MFC], displaying in a form
ms.assetid: c56185c4-12cb-40b1-b499-02b29ea83e3a
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1a7960780f1f83833e25c9a094a36314a299a042
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="displaying-and-manipulating-data-in-a-form"></a>Affichage et manipulation de données dans un formulaire
De nombreuses applications d’accès aux données sélectionnent les données et les affichent dans les champs dans un formulaire. La classe de base de données [CRecordView](../../mfc/reference/crecordview-class.md) vous donne un [CFormView](../../mfc/reference/cformview-class.md) objet directement connecté à un objet recordset. La vue de l’enregistrement utilise [échange de données de boîtes de dialogue (DDX)](../../mfc/dialog-data-exchange-and-validation.md) pour déplacer les valeurs des champs de l’enregistrement actif du jeu d’enregistrements pour les contrôles du formulaire et pour replacer les informations mises à jour vers le recordset. L’objet recordset et utilise à son tour, échange de champs d’enregistrements (RFX) pour transférer des données entre ses membres de données de champ et les colonnes correspondantes dans une table de la source de données.  
  
 Vous pouvez utiliser l’Assistant Application MFC ou **ajouter une classe** (comme décrit dans [Ajout d’un consommateur ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) pour créer la classe d’affichage et sa classe de recordset associé conjointement.  
  
 Vue d’enregistrement et son jeu d’enregistrements sont détruits lorsque vous fermez le document. Pour plus d’informations sur les vues des enregistrements, consultez [vues des enregistrements](../../data/record-views-mfc-data-access.md). Pour plus d’informations sur RFX, consultez [Record Field Exchange (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
## <a name="see-also"></a>Voir aussi  
 [ODBC et MFC](../../data/odbc/odbc-and-mfc.md)