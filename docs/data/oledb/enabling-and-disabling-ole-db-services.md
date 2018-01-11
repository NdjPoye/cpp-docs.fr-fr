---
title: "Activation et désactivation des Services OLE DB | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 445f97eb-32a8-41c2-ad26-1169f78a074f
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 59b1a50c44d5719cf3c699a14e5139d9e9816938
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="enabling-and-disabling-ole-db-services"></a>Activation et désactivation des services OLE DB
Le Gestionnaire de composants de Service OLE DB compare les propriétés spécifiées par le consommateur à celles prises en charge par le fournisseur pour déterminer si les composants de service individuels peuvent être appelés pour répondre à des fonctionnalités étendues demandées par le consommateur. Par exemple, si une application demande un curseur de défilement et le fournisseur prend en charge uniquement un curseur avant uniquement, le Gestionnaire de composants de Service appelle le composant de service de moteur de curseur Client pour fournir la fonctionnalité de défilement. Si l’application repose sur les fonctionnalités étendues prises en charge par défaut sur l’ensemble de lignes du fournisseur, et que l’application ne définit pas explicitement les propriétés à demander cette fonctionnalité, la fonctionnalité ne peut pas apparaître sur l’ensemble de lignes retourné par le Client Moteur de curseur. Pour être interopérable, les applications doivent toujours définir propriétés demander explicitement une fonctionnalité étendue quand cela est nécessaire.  
  
 Dans certains cas, il peut être nécessaire de désactiver des services OLE DB pour fonctionner avec les applications existantes qui font des hypothèses sur les caractéristiques d’un fournisseur. Services OLE DB offrent la possibilité de désactiver des services individuels, ou tous les services, sur une base de connexion par connexion ou pour toutes les applications à l’aide d’un fournisseur unique.  
  
## <a name="see-also"></a>Voir aussi  
 [Services et regroupement des ressources OLE DB](../../data/oledb/ole-db-resource-pooling-and-services.md)