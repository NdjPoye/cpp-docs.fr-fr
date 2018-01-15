---
title: "Agrégation | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- aggregation [C++]
- aggregate objects [C++]
ms.assetid: 7125bb8e-b269-4b50-9bba-295b467a54cc
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8dbb0332bc7e55464e5b8af9d0b57e236f23dc86
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="aggregation"></a>Agrégation
Il existe des cas de circonstances implémentation d’un objet pour tirer parti des services offerts par un autre objet prégénéré. En outre, il souhaite que cet objet s’affichent en tant que dans le cadre de la première. COM réalise cet objectif grâce à la relation contenant-contenu et d’agrégation.  
  
 L’agrégation signifie que l’objet de conteneur (externe) crée l’objet de contenu (interne) dans le cadre du processus de création et les interfaces de l’objet interne sont exposées en externe. Un objet permet de lui-même doit être agrégée ou non. S’il s’agit, il doit suivre certaines règles pour l’agrégation pour fonctionner correctement.  
  
 Principalement, tous les **IUnknown** des appels de méthode sur l’objet de relation contenant-contenu doivent déléguer à l’objet conteneur.  
  
## <a name="see-also"></a>Voir aussi  
 [Introduction à COM](../atl/introduction-to-com.md)   
 [Réutilisation d’objets](http://msdn.microsoft.com/library/windows/desktop/ms678443)

