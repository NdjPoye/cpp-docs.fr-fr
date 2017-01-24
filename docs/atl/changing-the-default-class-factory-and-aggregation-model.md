---
title: "Changing the Default Class Factory and Aggregation Model | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregation [C++], aggregation models"
  - "aggregation [C++], utiliser ATL"
  - "CComClassFactory class, making the default"
  - "CComCoClass class, default class factory and aggregation model"
  - "class factories, modifier l'éditeur par défaut"
  - "default class factory"
  - "default class factory, ATL"
  - "valeurs par défaut (C++), aggregation model in ATL"
  - "valeurs par défaut (C++), class factory"
ms.assetid: 6e040e95-0f38-4839-8a8b-c9800dd47e8c
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Changing the Default Class Factory and Aggregation Model
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les utilisations [CComCoClass](../atl/reference/ccomcoclass-class.md) ATL pour définir la fabrique de classes et le regroupement par défaut modèle pour votre objet.  `CComCoClass` spécifie les deux macros suivantes :  
  
-   [DECLARE\_CLASSFACTORY](../Topic/DECLARE_CLASSFACTORY.md) déclare la fabrique de classe pour être [CComClassFactory](../atl/reference/ccomclassfactory-class.md).  
  
-   [DECLARE\_AGGREGATABLE](../Topic/DECLARE_AGGREGATABLE.md) déclare que votre objet peut être regroupé.  
  
 Vous pouvez substituer l'une ou l'autre de ces valeurs par défaut en spécifiant une autre macro dans la définition de classe.  Par exemple, pour utiliser [CComClassFactory2](../atl/reference/ccomclassfactory2-class.md) au lieu d' `CComClassFactory`, spécifiez la macro de [DECLARE\_CLASSFACTORY2](../Topic/DECLARE_CLASSFACTORY2.md) :  
  
 [!code-cpp[NVC_ATL_COM#2](../atl/codesnippet/CPP/changing-the-default-class-factory-and-aggregation-model_1.h)]  
  
 Deux autres macros qui définissent une fabrique de classe sont [DECLARE\_CLASSFACTORY\_AUTO\_THREAD](../Topic/DECLARE_CLASSFACTORY_AUTO_THREAD.md) et [DECLARE\_CLASSFACTORY\_SINGLETON](../Topic/DECLARE_CLASSFACTORY_SINGLETON.md).  
  
 ATL utilise également le mécanisme d' `typedef` pour implémenter le comportement par défaut.  Par exemple, la macro d' `DECLARE_AGGREGATABLE` utilise `typedef` pour définir un type nommé **\_CreatorClass**, qui est ensuite référencé dans tout ATL.  Notez que dans une classe dérivée, `typedef` à l'aide de le même nom que les résultats d' `typedef` de classe de base dans ATL à votre définition et substituer le comportement par défaut.  
  
## Voir aussi  
 [Fundamentals of ATL COM Objects](../atl/fundamentals-of-atl-com-objects.md)   
 [Aggregation and Class Factory Macros](../atl/reference/aggregation-and-class-factory-macros.md)