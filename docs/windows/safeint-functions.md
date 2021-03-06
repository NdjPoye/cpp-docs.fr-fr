---
title: SafeInt, fonctions | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- functions, SafeInt
ms.assetid: fdc208e5-5d8a-41a9-8271-567fd438958d
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 97edd25abca3c9e80a35745165eedc93cc13a9b9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2018
---
# <a name="safeint-functions"></a>SafeInt, fonctions
La Bibliothèque SafeInt fournit plusieurs fonctions que vous pouvez utiliser sans créer d’instance de la [SafeInt, classe](../windows/safeint-class.md). Si vous souhaitez protéger une seule opération mathématique de dépassement sur les entiers, vous pouvez utiliser ces fonctions. Si vous souhaitez protéger plusieurs opérations mathématiques, vous devez créer `SafeInt` objets. Il est plus efficace de créer `SafeInt` objets que d’utiliser ces fonctions plusieurs fois.  
  
 Ces fonctions permettent de comparer ou effectuer des opérations mathématiques sur deux différents types de paramètres sans avoir à les convertir d’abord vers le même type.  
  
 Chacune de ces fonctions a deux types de modèle : `T` et `U`. Chacun de ces types peut être une valeur booléenne, un caractère ou un type intégral. Types intégraux peuvent être signés ou non signés et n’importe quelle taille de 8 bits à 64 bits.  
  
## <a name="in-this-section"></a>Dans cette section  
  
|Fonction|Description|  
|--------------|-----------------|  
|[SafeAdd](../windows/safeadd.md)|Ajoute deux nombres et protège contre le dépassement de capacité.|  
|[SafeCast](../windows/safecast.md)|Convertit un type de paramètre à un autre type.|  
|[SafeDivide](../windows/safedivide.md)|Divise deux nombres et protège contre la division par zéro.|  
|[SafeEquals](../windows/safeequals.md), [SafeGreaterThan](../windows/safegreaterthan.md), [SafeGreaterThanEquals](../windows/safegreaterthanequals.md), [SafeLessThan](../windows/safelessthan.md), [SafeLessThanEquals](../windows/safelessthanequals.md), [ SafeNotEquals](../windows/safenotequals.md)|Compare deux nombres. Ces fonctions permettent de comparer deux types de nombres sans modifier leurs types.|  
|[SafeModulus](../windows/safemodulus.md)|Effectue l’opération modulo de deux nombres.|  
|[SafeMultiply](../windows/safemultiply.md)|Multiplie deux nombres entre eux et protège contre le dépassement de capacité.|  
|[SafeSubtract](../windows/safesubtract.md)|Soustrait deux nombres et protège contre le dépassement de capacité.|  
  
## <a name="related-sections"></a>Rubriques connexes  
  
|Section|Description|  
|-------------|-----------------|  
|[SafeInt, classe](../windows/safeint-class.md)|La classe `SafeInt`.|  
|[SafeIntException Class](../windows/safeintexception-class.md)|La classe d’exception spécifique à la Bibliothèque SafeInt.|