---
title: DEFINE_COMMAND_EX | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DEFINE_COMMAND_EX
dev_langs: C++
helpviewer_keywords: DEFINE_COMMAND_EX macro
ms.assetid: d3e2ef20-1455-46d2-8499-8ab84bbb90a4
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 851b346c8fac955f1d82c0c43fdf75c4784ca04c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="definecommandex"></a>DEFINE_COMMAND_EX
Spécifie la commande permettant de créer l’ensemble de lignes lors de l’utilisation du [CCommand](../../data/oledb/ccommand-class.md) classe. Prend en charge les applications Unicode et ANSI.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
DEFINE_COMMAND_EX(  
x  
,   
wszCommand  
 )  
  
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