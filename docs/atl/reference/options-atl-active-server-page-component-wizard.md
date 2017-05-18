---
title: Options, Assistant de composant Active Server ATL | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.asp.options
dev_langs:
- C++
helpviewer_keywords:
- ATL Active Server Page Component Wizard, options
ms.assetid: 54f34e26-53c7-4456-9675-cb86e356bde0
caps.latest.revision: 12
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
ms.openlocfilehash: 608b7747c70286ed3bf9598036ac672881730815
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="options-atl-active-server-page-component-wizard"></a>Options, Assistant Composant ASP ATL
Utilisez cette page de l’Assistant composant Active Server Page ATL pour une efficacité accrue et la prise en charge de l’erreur pour l’objet.  
  
 Pour plus d’informations sur les projets ATL et les classes ATL COM, consultez [composants de bureau ATL COM](../../atl/atl-com-desktop-components.md).  
  
 **Modèle de thread**  
 Indique la méthode de gestion des threads. Par défaut, le projet utilise **Apartment** threads.  
  
 Consultez la page [en spécifiant le modèle de thread du projet](../../atl/specifying-the-threading-model-for-a-project-atl.md) pour plus d’informations.  
  
|Option|Description|  
|------------|-----------------|  
|`Single`|Spécifie que l’objet utilise le modèle de thread unique. Dans le modèle de thread unique, un objet s’exécute toujours dans le thread COM principal. Consultez la page [Single-Threaded Apartments](http://msdn.microsoft.com/library/windows/desktop/ms680112) et [InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390) pour plus d’informations.|  
|**Cloisonnement**|Spécifie que l’objet utilise le modèle de thread cloisonné. Cloisonnement de threads équivalent au seul. Chaque objet d’un composant à threads cloisonnés est assigné un cloisonnement pour son thread, pour la durée de vie de l’objet. Toutefois, plusieurs threads peuvent servir pour plusieurs objets. Chaque cloisonnement est lié à un thread spécifique et possède une pompe de messages Windows (par défaut).<br /><br /> Consultez la page [Single-Threaded Apartments](http://msdn.microsoft.com/library/windows/desktop/ms680112) pour plus d’informations.|  
|**Les deux**|Spécifie que l’objet peut utiliser cloisonné ou libre de thread, selon le type d’un thread est créé.|  
|**Gratuit**|Spécifie que l’objet utilise le modèle de thread libre. Ce qui équivaut à un modèle multithread cloisonné. Consultez la page [multithreads cloisonnés](http://msdn.microsoft.com/library/windows/desktop/ms693421) pour plus d’informations.|  
|**Neutre** (Windows 2000 uniquement)|Spécifie que l’objet suit les indications des multithreads cloisonnés, mais il peut s’exécuter sur n’importe quel type de thread.|  
  
 **Agrégation**  
 Indique si l’objet utilise [agrégation](http://msdn.microsoft.com/library/windows/desktop/ms686558). L’objet d’agrégat choisit les interfaces à exposer aux clients et les interfaces sont exposées comme si l’objet d’agrégat les implémenter. Les clients de l’objet d’agrégat communiquent uniquement avec l’objet d’agrégat.  
  
|Option|Description|  
|------------|-----------------|  
|**Oui**|Spécifie que l’objet peut être agrégé. Valeur par défaut.|  
|**No**|Spécifie que l’objet n’est pas agrégé.|  
|**Uniquement**|Spécifie que l’objet doit être agrégée.|  
  
 **Prise en charge**  
 (Description de l’élément à ajouter)  
  
|Option|Description|  
|------------|-----------------|  
|**ISupportErrorInfo**|Crée la prise en charge de la [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md) interface afin que l’objet puisse retourner des informations d’erreur au client.|  
|**Points de connexion**|Active les points de connexion pour votre objet en faisant dériver la classe de l’objet [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md).|  
|**Marshaleur libre de threads**|Crée un objet marshaleur libre de threads pour marshaler des pointeurs d’interface efficacement entre les threads dans le même processus. Disponible pour l’objet spécifiant **les** ou **gratuit** comme modèle de thread.|  
  
## <a name="see-also"></a>Voir aussi  
 [Assistant de composant Active Server ATL](../../atl/reference/atl-active-server-page-component-wizard.md)   
 [Composant de Active Server Page ATL](../../atl/reference/adding-an-atl-active-server-page-component.md)


