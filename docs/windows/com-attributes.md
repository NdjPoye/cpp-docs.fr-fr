---
title: "COM Attributes | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "attributes [C++], reference topics"
  - "attributes [COM]"
  - "COM, attributes"
ms.assetid: 52a5dd70-e8be-4bba-afd6-daf90fe689a0
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COM Attributes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les attributs COM injectent un code pour prendre en charge de nombreux domaines du développement COM et le développement du common langage runtime du.NET Framework.  Ces zones sont comprises entre l'implémentation personnalisée d'interface et de la prise en charge des interfaces existantes aux propriétés stock de prise en charge, des méthodes, les événements et.  En outre, la prise en charge est trouvée pour le composite et l'implémentation du contrôle ActiveX.  
  
|Attribut|Description|  
|--------------|-----------------|  
|[aggregatable](../windows/aggregatable.md)|indique qu'un contrôle peut être regroupé par un autre contrôle.|  
|[agrégats](../windows/aggregates.md)|indique qu'un contrôle regroupe la classe cible.|  
|[coclasse](../windows/coclass.md)|crée un objet COM, qui peut implémenter une interface COM.|  
|[com\_interface\_entry](../windows/com-interface-entry-cpp.md)|ajoute une entrée d'interface à un mappage COM.|  
|[implements\_category](../windows/implements-category.md)|Spécifie a implémenté des catégories de composants pour la classe.|  
|[progid](../windows/progid.md)|définit l'identificateur programmatique pour un contrôle.|  
|[rdx](../windows/rdx.md)|crée ou modifie une clé de Registre.|  
|[registration\_script](../windows/registration-script.md)|Exécute le script spécifié d'inscription.|  
|[requires\_category](../windows/requires-category.md)|spécifie des catégories de composant requis pour la classe.|  
|[support\_error\_information](../windows/support-error-info.md)|Prend en charge le rapport d'erreurs pour l'objet de la cible.|  
|[synchronisez](../windows/synchronize.md)|synchronise l'accès à une méthode.|  
|[threads](../windows/threading-cpp.md)|spécifie le modèle de thread pour un objet COM.|  
|[vi\_progid](../windows/vi-progid.md)|Définit un identificateur programmatique indépendant de la version d'un contrôle.|  
  
## Voir aussi  
 [Attributes by Group](../windows/attributes-by-group.md)