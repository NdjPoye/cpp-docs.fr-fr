---
title: "Aggregation and Class Factory Macros | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregation [C++], ATL macros"
  - "class factories, ATL macros"
ms.assetid: d99d379a-0eec-481f-8daa-252dac18f163
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# Aggregation and Class Factory Macros
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ces macros fournissent des façons de contrôler le regroupement et de déclarer les fabriques de classe.  
  
|||  
|-|-|  
|[DECLARE\_AGGREGATABLE](../Topic/DECLARE_AGGREGATABLE.md)|Déclare que votre objet peut être regroupé \(valeur par défaut\).|  
|[DECLARE\_CLASSFACTORY](../Topic/DECLARE_CLASSFACTORY.md)|Déclare la fabrique de classe pour être [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), la fabrique de classe par défaut ATL.|  
|[DECLARE\_CLASSFACTORY\_EX](../Topic/DECLARE_CLASSFACTORY_EX.md)|Déclare votre objet de fabrique de classe comme étant la fabrique de classe.|  
|[DECLARE\_CLASSFACTORY2](../Topic/DECLARE_CLASSFACTORY2.md)|Déclare [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) pour être la fabrique de classe.|  
|[DECLARE\_CLASSFACTORY\_AUTO\_THREAD](../Topic/DECLARE_CLASSFACTORY_AUTO_THREAD.md)|Déclare [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) pour être la fabrique de classe.|  
|[DECLARE\_CLASSFACTORY\_SINGLETON](../Topic/DECLARE_CLASSFACTORY_SINGLETON.md)|Déclare [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md) pour être la fabrique de classe.|  
|[DECLARE\_GET\_CONTROLLING\_UNKNOWN](../Topic/DECLARE_GET_CONTROLLING_UNKNOWN.md)|Déclare une fonction virtuelle d' `GetControllingUnknown` .|  
|[DECLARE\_NOT\_AGGREGATABLE](../Topic/DECLARE_NOT_AGGREGATABLE.md)|Déclare que votre objet ne peut pas être regroupé.|  
|[DECLARE\_ONLY\_AGGREGATABLE](../Topic/DECLARE_ONLY_AGGREGATABLE.md)|Déclare que votre objet doit être regroupé.|  
|[DECLARE\_POLY\_AGGREGATABLE](../Topic/DECLARE_POLY_AGGREGATABLE.md)|Contrôle la valeur de l'inconnu externe et déclare votre objet pouvant être regroupé en agrégats ou non pouvant être regroupé en agrégats, le cas échéant.|  
|[DECLARE\_PROTECT\_FINAL\_CONSTRUCT](../Topic/DECLARE_PROTECT_FINAL_CONSTRUCT.md)|Protège l'objet externe de la suppression pendant la construction d'un objet interne.|  
|[DECLARE\_VIEW\_STATUS](../Topic/DECLARE_VIEW_STATUS.md)|Spécifie des indicateurs de **VIEWSTATUS** au conteneur.|  
  
## Voir aussi  
 [Macros](../../atl/reference/atl-macros.md)