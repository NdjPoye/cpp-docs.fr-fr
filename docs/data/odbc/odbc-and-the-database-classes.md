---
title: "ODBC et les Classes de base de données | Documents Microsoft"
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
- database classes [C++], ODBC
- ODBC API functions [C++]
- ODBC classes [C++], MFC database classes
- MFC [C++], ODBC and
ms.assetid: b166f82d-6f85-4556-aac8-fb851235d22c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e3041a4fc027a8786fb62db7df6eaf486633ce97
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="odbc-and-the-database-classes"></a>ODBC et les classes de base de données
Les classes de base de données ODBC MFC encapsulent les appels de fonction API ODBC que vous effectueriez normalement vous-même dans le membre de fonctions de la [CDatabase](../../mfc/reference/cdatabase-class.md) et [CRecordset](../../mfc/reference/crecordset-class.md) classes. Par exemple, les séquences d’appel ODBC complexes, la liaison d’enregistrements retournés à des emplacements de stockage, la gestion des conditions d’erreur et d’autres opérations sont gérées automatiquement par les classes de base de données. Par conséquent, vous utilisez une interface de classe beaucoup plus simple pour manipuler des enregistrements d’un objet recordset.  
  
> [!NOTE]
>  Sources de données ODBC sont accessibles via les classes ODBC MFC, comme décrit dans cette rubrique, ou via les classes MFC DAO Data Access Object ().  
  
 Bien que les classes de base de données encapsulent la fonctionnalité ODBC, elles ne fournissent pas un mappage des fonctions API ODBC. Les classes de base de données fournissent un niveau supérieur d’abstraction, basé sur les objets d’accès aux données dans Microsoft Access et Microsoft Visual Basic. Pour plus d’informations, consultez [ODBC et MFC](../../data/odbc/odbc-and-mfc.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Éléments fondamentaux relatifs à ODBC](../../data/odbc/odbc-basics.md)