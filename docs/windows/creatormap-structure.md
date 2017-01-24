---
title: "CreatorMap, structure | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Details::CreatorMap"
  - "implements/Microsoft::WRL::Details::CreatorMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreatorMap (structure)"
ms.assetid: 94e40927-90c3-4107-bca3-3ad2dc4beda9
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CreatorMap, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
struct CreatorMap;  
```  
  
## Remarques  
 Contient des informations sur l'initialisation, l'enregistrement et l'effacement d'objets.  
  
 CreatorMap contient les informations suivantes:  
  
-   Initialiser, enregistrer, et effacer des objets.  
  
-   Comparer des données d'activation en fonction d'un COM classique ou d'une fabrique [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  
  
-   Informations sur le cache de fabrique et le nom du serveur pour une interface.  
  
## Membres  
  
### Données membres publiques  
  
|Name|Description|  
|----------|-----------------|  
|[CreatorMap::activationId, données de membre](../windows/creatormap-activationid-data-member.md)|Représente un ID d'objet identifié soit par un ID de classe COM classique ou par un nom [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].|  
|[CreatorMap::factoryCache, données de membre](../windows/creatormap-factorycache-data-member.md)|Stocke le pointeur dans le cache de fabrique pour le CreatorMap.|  
|[CreatorMap::factoryCreator, données de membre](../windows/creatormap-factorycreator-data-member.md)|Crée une fabrique pour le CreatorMap spécifié.|  
|[CreatorMap::serverName, données de membre](../windows/creatormap-servername-data-member.md)|Stocke le nom du serveur pour le CreatorMap.|  
  
## Hiérarchie d'héritage  
 `CreatorMap`  
  
## Configuration requise  
 **En\-tête:** module.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)