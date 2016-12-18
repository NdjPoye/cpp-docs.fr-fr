---
title: "Options, Assistant Composant ASP ATL | Microsoft Docs"
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
  - "vc.codewiz.class.atl.asp.options"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistant Composant ASP ATL, options"
ms.assetid: 54f34e26-53c7-4456-9675-cb86e356bde0
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Options, Assistant Composant ASP ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisez la page Options de l'Assistant Composant Active Server Page ATL pour améliorer l'efficacité et la prise en charge des erreurs de l'objet.  
  
 Pour plus d'informations sur les projets ATL et les classes ATL COM, consultez [ATL COM Desktop Components](../../atl/atl-com-desktop-components.md).  
  
 **Modèle de thread**  
 Indique la méthode utilisée pour la gestion des threads.  Par défaut, le projet utilise le modèle de thread **cloisonné**.  
  
 Pour plus d'informations, consultez [Spécification du modèle de thread du projet](../../atl/specifying-the-threading-model-for-a-project-atl.md).  
  
|Option|Description|  
|------------|-----------------|  
|`Single`|Spécifie que l'objet utilise le modèle de thread unique.  Dans le modèle monothread, un objet s'exécute toujours dans le thread COM principal.  Pour plus d'informations, consultez [threads cloisonnés \(Single\-Threaded Apartments, STA\)](http://msdn.microsoft.com/library/windows/desktop/ms680112) et [InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390).|  
|**Apartment \(cloisonné\)**|Spécifie que l'objet utilise le modèle de thread cloisonné.  Équivaut au mode STA \(Single Thread Apartment\).  Chaque objet d'un composant à thread cloisonné se voit assigner un cloisonnement pour son thread, pour toute la durée de vie de l'objet. Il est toutefois possible d'utiliser plusieurs threads pour plusieurs objets.  Chaque cloisonnement est lié à un thread spécifique et possède une pompe de messages Windows \(par défaut\).<br /><br /> Pour plus d'informations, consultez [threads cloisonnés \(Single\-Threaded Apartments, STA\)](http://msdn.microsoft.com/library/windows/desktop/ms680112).|  
|**Les deux**|Spécifie que l'objet peut utiliser le modèle de thread Apartment \(cloisonné\) ou Free \(libre\), selon le type de thread créé.|  
|**Free \(libre\)**|Spécifie que l'objet utilise le modèle libre de threads,  ce qui équivaut à un modèle multithread cloisonné.  Pour plus d'informations, consultez [multithreads cloisonnés](http://msdn.microsoft.com/library/windows/desktop/ms693421).|  
|**Neutral** \(neutre : Windows 2000 uniquement\)|Spécifie que l'objet suit les indications des multithreads cloisonnées, mais qu'il peut s'exécuter sur n'importe quel type de thread.|  
  
 **Aggregation**  
 Indique si l'objet utilise l'[agrégation](http://msdn.microsoft.com/library/windows/desktop/ms686558).  L'objet d'agrégat choisit les interfaces à exposer aux clients et celles\-ci sont exposées comme si l'objet d'agrégat les implémentait.  Les clients de l'objet d'agrégat communiquent uniquement avec l'objet d'agrégat.  
  
|Option|Description|  
|------------|-----------------|  
|**Oui**|Spécifie que l'objet peut être regroupé en agrégats.  Valeur par défaut.|  
|**Non**|Spécifie que l'objet n'est pas regroupé en agrégats.|  
|**Uniquement**|Spécifie que l'objet doit être regroupé en agrégats.|  
  
 **Prise en charge**  
 \(Description d'élément à ajouter\)  
  
|Option|Description|  
|------------|-----------------|  
|**ISupportErrorInfo**|Crée une prise en charge pour l'interface [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md) afin que l'objet puisse retourner au client des informations sur les erreurs.|  
|**Points de connexion**|Active les points de connexion pour votre objet en faisant dériver la classe de l'objet de [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md).|  
|**Marshaleur libre de threads \(FTM\)**|Crée un objet FTM \(Free\-Threaded Marshaler\) pour marshaler efficacement les pointeurs d'interface situés entre les threads du même processus.  Disponible pour l'objet si vous spécifiez **Les deux** ou **Libre** comme modèle de thread.|  
  
## Voir aussi  
 [Composant Active Server Page ATL \(Assistant\)](../../atl/reference/atl-active-server-page-component-wizard.md)   
 [ATL Active Server Page Component](../../atl/reference/adding-an-atl-active-server-page-component.md)