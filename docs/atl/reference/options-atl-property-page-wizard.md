---
title: "Options, Assistant Page de propriétés ATL | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.ppg.options
dev_langs:
- C++
helpviewer_keywords:
- ATL Property Page Wizard, options
ms.assetid: a7107779-b2ea-4f99-b84b-7f3e0c504bc8
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: bea768cf456fadfbe05e450c5e6652d1f7f378f5
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="options-atl-property-page-wizard"></a>Options, Assistant Page de propriétés ATL
Utilisez cette page de l’Assistant pour définir le niveau d’agrégation et le modèle de thread de page de propriétés que vous créez.  
  
 **Modèle de thread**  
 Spécifie le modèle de thread utilisé par la page de propriétés.  
  
 Consultez la page [en spécifiant le modèle de thread du projet](../../atl/specifying-the-threading-model-for-a-project-atl.md) pour plus d’informations.  
  
|Option|Description|  
|------------|-----------------|  
|`Single`|La page de propriétés s’exécute uniquement dans le thread COM principal.|  
|**Cloisonnement**|La page de propriétés peut être créée dans n’importe quel thread unique cloisonné. Valeur par défaut.|  
  
 **Agrégation**  
 Ajoute la prise en charge de l’agrégation de la page de propriétés que vous créez. Consultez la page [agrégation](../../atl/aggregation.md) pour plus d’informations.  
  
|Option|Description|  
|------------|-----------------|  
|**Oui**|Créer une page de propriétés qui peut être regroupée.|  
|**No**|Créer une page de propriétés qui ne peut pas être agrégée.|  
|**Uniquement**|Créer une page de propriétés qui ne peut être instanciée par le biais d’agrégation.|  
  
## <a name="see-also"></a>Voir aussi  
 [Assistant Page de propriétés ATL](../../atl/reference/atl-property-page-wizard.md)   
 [Chaînes, Assistant Page de propriétés ATL](../../atl/reference/strings-atl-property-page-wizard.md)


