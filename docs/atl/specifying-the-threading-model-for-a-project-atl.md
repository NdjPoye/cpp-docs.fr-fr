---
title: "Spécification du modèle de thread pour un projet (ATL) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- _ATL_FREE_THREADED macro
- _ATL_APARTMENT_THREADED macro
- ATL, multithreading
- threading [ATL], models
- _ATL_SINGLE_THREADED macro
ms.assetid: 6b571078-521c-4f3e-9f08-482aa235a822
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a4c115b326d2cdfe82a0466461bd378fd1b4be80
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="specifying-the-threading-model-for-a-project-atl"></a>Spécification du modèle de thread pour un projet (ATL)
Les macros suivantes sont disponibles pour spécifier le modèle de thread d’un projet ATL :  
  
|Macro|Instructions d’utilisation|  
|-----------|--------------------------|  
|_ATL_SINGLE_THREADED|Définir si tous les objets utilisent le modèle de thread unique.|  
|_ATL_APARTMENT_THREADED|Définir si un ou plusieurs de vos objets utilisent le cloisonnement des threads.|  
|_ATL_FREE_THREADED|Définir si un ou plusieurs de vos objets utilisent le threading de libre ou neutre. Le code existant peut contenir des références à la macro équivalente [_ATL_MULTI_THREADED](reference/compiler-options-macros.md#_atl_multi_threaded).|  
  
 Si vous ne définissez pas une de ces macros pour votre projet, _ATL_FREE_THREADED sera appliquée.  
  
 Les macros affectent les performances d’exécution comme suit :  
  
-   En spécifiant la macro qui correspond aux objets dans votre projet peut améliorer les performances d’exécution.  
  
-   Spécification d’un niveau supérieur de la macro, par exemple, si vous spécifiez _ATL_APARTMENT_THREADED lorsque tous les objets sont, réduit légèrement les performances d’exécution.  
  
-   Spécification d’un niveau inférieur de la macro, par exemple, si vous spécifiez _ATL_SINGLE_THREADED lorsqu’un ou plusieurs de vos objets utilisent le modèle de thread cloisonné ou libre, peut entraîner de votre application échoue au moment de l’exécution.  
  
 Consultez [Options, Assistant objet Simple ATL](../atl/reference/options-atl-simple-object-wizard.md) pour obtenir une description de la thread les modèles disponibles pour un objet ATL.  
  
## <a name="see-also"></a>Voir aussi  
 [Concepts](../atl/active-template-library-atl-concepts.md)

