---
title: "Les modifications que vous pouvez apporter au Code par défaut (MFC Data Access) | Documents Microsoft"
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
- record views [C++], customizing default code
ms.assetid: 9992ed37-a6bf-45a5-a572-5c14e42b6628
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 197277a68131c9d63e3eab2f1404cf97169be1f3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="changes-you-might-make-to-the-default-code--mfc-data-access"></a>Modifications possibles dans le code par défaut (Accès aux données MFC)
Le [Assistant Application MFC](../mfc/reference/database-support-mfc-application-wizard.md) écrit une classe de recordset qui sélectionne tous les enregistrements dans une table unique. Vous souhaiterez souvent modifier ce comportement d'une plusieurs des manières suivantes :  
  
-   Définir un filtre ou un ordre de tri pour le recordset. Cela dans `OnInitialUpdate` une fois l’objet recordset construit mais avant son **ouvrir** fonction membre est appelée. Pour plus d’informations, consultez [Recordset : filtrage d’enregistrements (ODBC)](../data/odbc/recordset-filtering-records-odbc.md) et [Recordset : tri d’enregistrements (ODBC)](../data/odbc/recordset-sorting-records-odbc.md).  
  
-   Paramétrer le recordset. Spécifiez la valeur réelle du paramètre au moment de l'exécution après le filtre. Pour plus d’informations, consultez [Recordset : paramétrage d’un Recordset (ODBC)](../data/odbc/recordset-parameterizing-a-recordset-odbc.md)  
  
-   Passez la chaîne SQL personnalisée à la [ouvrir](../mfc/reference/crecordset-class.md#open) fonction membre. Pour en savoir plus sur ce que vous pouvez accomplir avec cette technique, consultez [SQL : personnalisation du Recordset SQL instruction (ODBC)](../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).  
  
## <a name="see-also"></a>Voir aussi  
 [À l’aide d’une vue d’enregistrement](../data/using-a-record-view-mfc-data-access.md)