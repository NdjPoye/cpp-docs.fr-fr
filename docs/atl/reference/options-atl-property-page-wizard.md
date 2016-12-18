---
title: "Options, Assistant Page de propri&#233;t&#233;s ATL | Microsoft Docs"
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
  - "vc.codewiz.class.atl.ppg.options"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistant Page de propriétés ATL, options"
ms.assetid: a7107779-b2ea-4f99-b84b-7f3e0c504bc8
caps.latest.revision: 13
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Options, Assistant Page de propri&#233;t&#233;s ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisez cette page de l'Assistant pour définir le modèle de thread et le niveau d'agrégation de la page de propriétés que vous créez.  
  
 **Modèle de thread**  
 Spécifie le modèle de thread utilisé par la page de propriétés.  
  
 Pour plus d'informations, consultez [Spécification du modèle de thread du projet](../../atl/specifying-the-threading-model-for-a-project-atl.md).  
  
|Option|Description|  
|------------|-----------------|  
|`Single`|La page de propriétés s'exécute uniquement dans le thread COM principal.|  
|**Apartment \(cloisonné\)**|La page de propriétés peut être créée dans n'importe quel mode STA \(Single Thread Apartment\).  Valeur par défaut.|  
  
 **Aggregation**  
 Ajoute la prise en charge de l'agrégation pour la page de propriétés que vous créez.  Pour plus d'informations, consultez [Agrégation](../../atl/aggregation.md).  
  
|Option|Description|  
|------------|-----------------|  
|**Oui**|Crée une page de propriétés pouvant être regroupée en agrégats.|  
|**Non**|Crée une page de propriétés ne pouvant pas être regroupée en agrégats.|  
|**Uniquement**|Crée une page de propriétés qui ne peut être instanciée qu'à l'aide de l'agrégation.|  
  
## Voir aussi  
 [Assistant Page de propriétés ATL](../../atl/reference/atl-property-page-wizard.md)   
 [Chaînes, Assistant Page de propriétés ATL](../../atl/reference/strings-atl-property-page-wizard.md)