---
title: DEFINE_COMMAND_EX | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- DEFINE_COMMAND_EX
dev_langs:
- C++
helpviewer_keywords:
- DEFINE_COMMAND_EX macro
ms.assetid: d3e2ef20-1455-46d2-8499-8ab84bbb90a4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e3fb4ce434f578ed79f3ed086adf73a6a49da870
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="definecommandex"></a>DEFINE_COMMAND_EX
Spécifie la commande permettant de créer l’ensemble de lignes lors de l’utilisation du [CCommand](../../data/oledb/ccommand-class.md) classe. Prend en charge les applications Unicode et ANSI.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
DEFINE_COMMAND_EX(x, wszCommand)  
  
```  
  
#### <a name="parameters"></a>Paramètres  
 *x*  
 [in] Le nom de la classe d’enregistrement (commande) utilisateur.  
  
 `wszCommand`  
 [in] La chaîne de commande permettant de créer l’ensemble de lignes lors de l’utilisation [CCommand](../../data/oledb/ccommand-class.md).  
  
## <a name="remarks"></a>Notes  
 La chaîne de commande que vous spécifiez sera être utilisée en tant que la valeur par défaut si vous ne spécifiez pas de texte de la commande dans le [CCommand::Open](../../data/oledb/ccommand-open.md) (méthode).  
  
 Cette macro accepte des chaînes Unicode, quel que soit le type d’application. Cette macro est préférée sur [DEFINE_COMMAND](../../data/oledb/define-command.md) , car il prend en charge Unicode, ainsi que les applications ANSI.  
  
## <a name="example"></a>Exemple  
 Consultez [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md).  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [Macros et fonctions globales pour les modèles du consommateur OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)