---
title: Commandes et Tables | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumer templates, table support
- CCommand class, OLE DB consumer templates
- commands [C++], OLE DB Consumer Templates
- CTable class
- CAccessorRowset class, command and table classes
- rowsets, accessing
- tables [C++], OLE DB Consumer Templates
- OLE DB consumer templates, command support
ms.assetid: 4bd3787b-6d26-40a9-be0c-083080537c12
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b3500b5b39e4f6e483789cdc13a055b2fe45fa39
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="commands-and-tables"></a>Commandes et tables
Commandes et tables permettent d’accéder aux ensembles de lignes ; Autrement dit, ouvrir des ensembles de lignes, exécuter des commandes et lier les colonnes. Le [CCommand](../../data/oledb/ccommand-class.md) et [CTable](../../data/oledb/ctable-class.md) classes instancient les objets de commande et de table, respectivement. Ces classes dérivent [CAccessorRowset](../../data/oledb/caccessorrowset-class.md) comme indiqué dans l’illustration suivante.  
  
 ![CCommand et CTable](../../data/oledb/media/vccommandstables.gif "vccommandstables")  
Les Classes de Table et de commande  
  
 Dans le tableau précédent, `TAccessor` peut être n’importe quel type d’accesseur répertorié dans [Types d’accesseurs](../../data/oledb/accessors-and-rowsets.md). *TRowset* peut être n’importe quel type d’ensemble de lignes répertoriée dans [Types de l’ensemble de lignes](../../data/oledb/accessors-and-rowsets.md). *TMultiple* Spécifie le type de résultat (un seul ou plusieurs de jeu de résultats).  
  
 Le [Assistant Consommateur OLE DB ATL](../../atl/reference/atl-ole-db-consumer-wizard.md) vous permet de spécifier si un objet de commande ou de table.  
  
-   Pour les sources de données sans les commandes, vous pouvez utiliser la `CTable` classe. Vous l’utilisez généralement pour les ensembles de lignes simples qui ne spécifiez aucun paramètre et exigent aucun résultat multiple. Cette classe simple ouvre une table sur une source de données à l’aide d’un nom de table que vous spécifiez.  
  
-   Pour les sources de données qui prennent en charge les commandes, vous pouvez utiliser la `CCommand` classe à la place. Pour exécuter une commande, appelez [ouvrir](../../data/oledb/ccommand-open.md) sur cette classe. En guise d’alternative, vous pouvez appeler `Prepare` pour préparer une commande que vous souhaitez exécuter plusieurs fois.  
  
     **CCommand** possède trois arguments template : un type d’accesseur, un type d’ensemble de lignes et un type de résultat (`CNoMultipleResults`, par défaut, ou `CMultipleResults`). Si vous spécifiez `CMultipleResults`, le `CCommand` classe prend en charge la **IMultipleResults** interface et gère plusieurs ensembles de lignes. Le [DBVIEWER](http://msdn.microsoft.com/en-us/07620f99-c347-4d09-9ebc-2459e8049832) montre comment gérer les résultats multiples.  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)