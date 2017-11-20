---
title: OLE DB Services et regroupement des ressources | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- resource pooling [OLE DB], provider requirements
- OLE DB, resource pooling
- service providers [OLE DB]
- OLE DB services [OLE DB], provider requirements
- OLE DB services [OLE DB]
- OLE DB providers, resource pooling
ms.assetid: 360c36e2-25ae-4caf-8ee7-d4a6b6898f68
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e2b3500c90455c7f180f16eae3c56433f57d0492
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="ole-db-resource-pooling-and-services"></a>Services et regroupement des ressources OLE DB
Pour fonctionner correctement avec le regroupement OLE DB, ou avec n’importe quel service OLE DB, votre fournisseur doit prendre en charge le regroupement de tous les objets. Il s’agit d’une exigence de tout OLE DB fournisseur 1.5 ou ultérieure. Il est essentiel pour tirer parti des services. Les fournisseurs qui ne prennent pas en charge l’agrégation ne peut pas être mis en pool et des services supplémentaires sont fournies.  
  
 Pour être mis en pool, fournisseurs doivent prendre en charge le modèle de thread libre. Le pool de ressources détermine le modèle de thread du fournisseur en fonction de la **DBPROP_THREADMODEL** propriété.  
  
 Si le fournisseur a un état de connexion global qui peut changer pendant que la source de données est dans un état initialisé, il doit prendre en charge la nouvelle **DBPROP_RESETDATASOURCE** propriété. Cette propriété est appelée avant une connexion est réutilisée et de donner la possibilité de nettoyer l’état avant son utilisation suivante au fournisseur. Si le fournisseur ne peut pas nettoyer un état associé à la connexion, elle peut retourner **DBPROPSTATUS_NOTSETTABLE** pour la propriété et la connexion ne seront pas réutilisées.  
  
 Les fournisseurs qui se connectent à une base de données distante et peuvent détecter si que la connexion peut être perdue doit prendre en charge la **DBPROP_CONNECTIONSTATUS** propriété. Cette propriété donne aux services OLE DB la possibilité de détecter les connexions mortes et assurez-vous qu’ils ne sont pas retournées au pool.  
  
 Enfin, l’inscription de transaction automatique ne fonctionne généralement pas, sauf si elle est implémentée au même niveau que le regroupement. Les fournisseurs qui prennent en charge l’inscription de transaction automatique eux-mêmes doivent prendre en charge la désactivation de cette inscription en exposant la **DBPROP_INIT_OLEDBSERVICES** de propriété et de désactiver l’inscription si le **DBPROPVAL_OS_ TXNENLISTMENT** est désélectionnée.  
  
## <a name="see-also"></a>Voir aussi  
 [Techniques avancées du fournisseur](../../data/oledb/advanced-provider-techniques.md)