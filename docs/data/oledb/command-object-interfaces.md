---
title: "Interfaces de l’objet de commande | Documents Microsoft"
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
- command object interfaces [C++]
- command objects [OLE DB]
- OLE DB [C++], command object interfaces
ms.assetid: dacff5ae-252c-4f20-9ad7-4e602cc48536
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a26004edcd4b1e32bb7dd960ce927786296ef44b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="command-object-interfaces"></a>Interfaces de l'objet de commande
L’objet de commande utilise le `IAccessor` interface afin de spécifier des liaisons de paramètres. Le consommateur appelle `IAccessor::CreateAccessor`, en lui passant un tableau de `DBBINDING` structures. `DBBINDING` contient des informations sur les liaisons de colonne (par exemple, le type et la longueur). Le fournisseur reçoit les structures et détermine comment les données doivent être transférées et si des conversions sont nécessaires.  
  
 Le `ICommandText` interface fournit un moyen de spécifier une commande de texte. Le `ICommandProperties` interface gère toutes les propriétés de commande.  
  
## <a name="see-also"></a>Voir aussi  
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)