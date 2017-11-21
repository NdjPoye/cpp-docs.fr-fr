---
title: "RuntimeClassType (énumération) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::RuntimeClassType
dev_langs: C++
helpviewer_keywords: RuntimeClassType enumeration
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 222f7d9ada76e43fa71658faa7c61e5369abd3db
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="runtimeclasstype-enumeration"></a>RuntimeClassType (énumération)
Spécifie le type de [RuntimeClass](../windows/runtimeclass-class.md) instance qui est pris en charge.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
enum RuntimeClassType;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="values"></a>Valeurs  
  
|Nom|Description|  
|----------|-----------------|  
|`ClassicCom`|Classe d’exécution COM classique.|  
|`Delegate`|Équivalent à **ClassicCom**.|  
|`InhibitFtmBase`|Désactive `FtmBase` prise en charge lors de la `__WRL_CONFIGURATION_LEGACY__` n’est pas défini.|  
|`InhibitWeakReference`|Désactive la prise en charge de la référence faible.|  
|`WinRt`|Une classe Windows Runtime.|  
|`WinRtClassicComMix`|Combinaison de `WinRt` et `ClassicCom`.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** implements.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)