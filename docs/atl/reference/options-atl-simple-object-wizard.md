---
title: "Options, Assistant Objet simple ATL | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.simple.options"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistant Objet simple ATL, options"
ms.assetid: 125fe179-942d-4181-8b82-33e92e1fd779
caps.latest.revision: 14
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Options, Assistant Objet simple ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisez cette page de l'Assistant Objet simple ATL pour améliorer l'efficacité et la prise en charge des erreurs de l'objet.  
  
 Pour plus d'informations sur les projets ATL et les classes ATL COM, consultez [ATL COM Desktop Components](../../atl/atl-com-desktop-components.md).  
  
 **Modèle de thread**  
 Indique la méthode utilisée pour la gestion des threads.  Par défaut, le projet utilise le modèle de thread **cloisonné**.  
  
 Pour plus d'informations, consultez [Spécification du modèle de thread du projet](../../atl/specifying-the-threading-model-for-a-project-atl.md).  
  
|Option|Description|  
|------------|-----------------|  
|`Single`|Spécifie que l'objet s'exécute toujours dans le thread COM principal.  Pour plus d'informations, consultez [threads cloisonnés \(Single\-Threaded Apartments, STA\)](http://msdn.microsoft.com/library/windows/desktop/ms680112) et [InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390).|  
|**Apartment \(cloisonné\)**|Spécifie que l'objet utilise le modèle de thread cloisonné.  Équivaut au mode STA \(Single Thread Apartment\).  Chaque objet d'un composant à thread cloisonné se voit assigner un cloisonnement pour son thread, pour toute la durée de vie de l'objet. Il est toutefois possible d'utiliser plusieurs threads pour plusieurs objets.  Chaque cloisonnement est lié à un thread spécifique et possède une pompe de messages Windows \(par défaut\).<br /><br /> Pour plus d'informations, consultez [threads cloisonnés \(Single\-Threaded Apartments, STA\)](http://msdn.microsoft.com/library/windows/desktop/ms680112).|  
|**Les deux**|Spécifie que l'objet peut utiliser le modèle de thread Apartment \(cloisonné\) ou Free \(libre\), selon le type de thread créé.|  
|**Free \(libre\)**|Spécifie que l'objet utilise le modèle libre de threads,  ce qui équivaut à un modèle multithread cloisonné.  Pour plus d'informations, consultez [multithreads cloisonnés](http://msdn.microsoft.com/library/windows/desktop/ms693421).|  
|**Neutral** \(neutre : Windows 2000 uniquement\)|Spécifie que l'objet suit les indications des multithreads cloisonnées, mais qu'il peut s'exécuter sur n'importe quel type de thread.|  
  
 **Aggregation**  
 Indique si l'objet utilise l'[agrégation](http://msdn.microsoft.com/library/windows/desktop/ms686558).  L'objet d'agrégat choisit les interfaces à exposer aux clients et celles\-ci sont exposées comme si l'objet d'agrégat les implémentait.  Les clients de l'objet d'agrégat communiquent uniquement avec l'objet d'agrégat.  
  
|Option|Description|  
|------------|-----------------|  
|Oui|Spécifie que l'objet peut être regroupé en agrégats.  Valeur par défaut.|  
|Non|Spécifie que l'objet n'est pas regroupé en agrégats.|  
|Uniquement|Spécifie que l'objet doit être regroupé en agrégats.|  
  
 **Interface**  
 Indique le type d'interface pris en charge par l'objet.  Par défaut, l'objet prend en charge une interface double.  
  
|Option|Description|  
|------------|-----------------|  
|**Double**|Spécifie que l'objet prend en charge une interface double \(sa table de fonctions virtuelles, vtable, possède des fonctions d'interface personnalisées, ainsi que des méthodes `IDispatch` de liaison tardive\).  Autorise à la fois les clients COM et les [contrôleurs Automation](../../mfc/automation-clients.md) à accéder à l'objet.  Valeur par défaut.|  
|**Personnalisé**|Spécifie que l'objet prend en charge une interface personnalisée \(sa table de fonctions virtuelles, vtable, possède des fonctions d'interface personnalisées\).  Une interface personnalisée peut être plus rapide qu'une interface double, particulièrement pour les opérations interprocessus.<br /><br /> -   **Automation compatible** permet aux contrôleurs automation pour accéder à un objet qui assure la prise en charge personnalisée de l'interface.|  
  
 **Prise en charge**  
 Indique les prises en charge supplémentaires pour l'objet.  
  
|Option|Description|  
|------------|-----------------|  
|**ISupportErrorInfo**|Crée une prise en charge pour l'interface [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md) afin que l'objet puisse retourner au client des informations sur les erreurs.|  
|**Points de connexion**|Active les points de connexion pour votre objet en faisant dériver la classe de l'objet de [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md).|  
|**Marshaleur libre de threads \(FTM\)**|Crée un objet FTM \(Free\-Threaded Marshaler\) pour marshaler efficacement les pointeurs d'interface situés entre les threads du même processus.  Disponible pour l'objet si vous spécifiez **Les deux** comme modèle de thread.|  
|**IObjectWithSite \(prise en charge d'objet IE\)**|Implémente [IObjectWithSiteImpl](../../atl/reference/iobjectwithsiteimpl-class.md), ce qui permet de prendre facilement en charge la communication entre un objet et son site dans un conteneur.|  
  
## Voir aussi  
 [Objet simple ATL \(Assistant\)](../../atl/reference/atl-simple-object-wizard.md)   
 [ATL Simple Object](../../atl/reference/adding-an-atl-simple-object.md)   
 [Problèmes de threading du serveur in\-process](http://msdn.microsoft.com/library/windows/desktop/ms687205)