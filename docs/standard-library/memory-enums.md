---
title: "&lt;memory&gt;, énumérations | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b9be0a7b-0beb-40b2-8183-911de371c6b9
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 9c3440495d77b788658cffefc917d9960ca1f833
ms.lasthandoff: 02/24/2017

---
# <a name="ltmemorygt-enums"></a>&lt;memory&gt;, énumérations
||  
|-|  
|[pointer_safety, énumérations](#pointer_safety_enumeration)|  
  
##  <a name="a-namepointersafetyenumerationa--pointersafety-enumeration"></a><a name="pointer_safety_enumeration"></a>  pointer_safety, énumération  
 Énumération des valeurs possibles retournées par `get_pointer_safety`.  
  
class pointer_safety { relaxed, preferred, strict };  
  
### <a name="remarks"></a>Notes  
 L’`enum` à étendue définit les valeurs qui peuvent être retournées par `get_pointer_safety``()` :  
  
 `relaxed` : les pointeurs qui ne sont pas dérivés de manière sécurisée (pointeurs vers des objets d’alloués ou déclarés) sont traités comme ceux qui sont dérivés de manière sécurisée.  
  
 `preferred` : comme avant, mais les pointeurs qui ne sont pas dérivés de manière sécurisée ne doivent pas être déréférencés.  
  
 `strict` : les pointeurs qui ne sont pas dérivés de manière sécurisée peuvent être traités différemment de ceux qui sont dérivés de manière sécurisée.  
  
## <a name="see-also"></a>Voir aussi  
 [\<memory>](../standard-library/memory.md)




