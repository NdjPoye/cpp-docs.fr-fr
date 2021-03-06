---
title: Modification de la fabrique de classe par défaut et le modèle d’agrégation | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactory class, making the default
- aggregation [C++], using ATL
- aggregation [C++], aggregation models
- defaults [C++], aggregation model in ATL
- default class factory
- class factories, changing default
- CComCoClass class, default class factory and aggregation model
- default class factory, ATL
- defaults [C++], class factory
ms.assetid: 6e040e95-0f38-4839-8a8b-c9800dd47e8c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ce64f2162aa0d5cdf5bcf5e16b56b6989fcaf1ee
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="changing-the-default-class-factory-and-aggregation-model"></a>Modification de la fabrique de classe par défaut et le modèle d’agrégation
ATL utilise [CComCoClass](../atl/reference/ccomcoclass-class.md) pour définir le modèle par défaut classe fabrique et l’agrégation pour votre objet. `CComCoClass` Spécifie les deux macros suivantes :  
  
-   [DECLARE_CLASSFACTORY](reference/aggregation-and-class-factory-macros.md#declare_classfactory) déclare la fabrique de classe [CComClassFactory](../atl/reference/ccomclassfactory-class.md).  
  
-   [DECLARE_AGGREGATABLE](reference/aggregation-and-class-factory-macros.md#declare_aggregatable) déclare que votre objet peut être agrégée.  
  
 Vous pouvez remplacer ces valeurs par défaut en spécifiant une autre macro dans votre définition de classe. Par exemple, pour utiliser [CComClassFactory2](../atl/reference/ccomclassfactory2-class.md) au lieu de `CComClassFactory`, spécifiez la [macro DECLARE_CLASSFACTORY2](reference/aggregation-and-class-factory-macros.md#declare_classfactory2) macro :  
  
 [!code-cpp[NVC_ATL_COM#2](../atl/codesnippet/cpp/changing-the-default-class-factory-and-aggregation-model_1.h)]  
  
 Deux autres macros qui définissent une fabrique de classe sont [DECLARE_CLASSFACTORY_AUTO_THREAD](reference/aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) et [DECLARE_CLASSFACTORY_SINGLETON](reference/aggregation-and-class-factory-macros.md#declare_classfactory_singleton).  
  
 ATL utilise également le `typedef` mécanisme pour implémenter le comportement par défaut. Par exemple, le `DECLARE_AGGREGATABLE` macro utilise `typedef` pour définir un type appelé **_CreatorClass**, qui est ensuite référencé dans ATL. Notez que dans une classe dérivée, un `typedef` à l’aide du même nom que la classe de base `typedef` entraîne ATL à l’aide de la définition et la substitution du comportement par défaut.  
  
## <a name="see-also"></a>Voir aussi  
 [Notions de base des objets ATL COM](../atl/fundamentals-of-atl-com-objects.md)   
 [Agrégation et macros de fabrique de classe](../atl/reference/aggregation-and-class-factory-macros.md)

