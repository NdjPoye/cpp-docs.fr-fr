---
title: '&lt;memory&gt;, énumérations | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- memory/std::pointer_safety
ms.assetid: b9be0a7b-0beb-40b2-8183-911de371c6b9
caps.latest.revision: 11
manager: ghogen
ms.openlocfilehash: 035175b2fea506fa341e260f042ae426e85421e4
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="ltmemorygt-enums"></a>&lt;memory&gt;, énumérations

||
|-|
|[pointer_safety](#pointer_safety)|

## <a name="pointer_safety"></a>  pointer_safety, énumération

Énumération des valeurs possibles retournées par `get_pointer_safety`.

class pointer_safety { relaxed, preferred, strict };

### <a name="remarks"></a>Notes

L’`enum` à étendue définit les valeurs qui peuvent être retournées par `get_pointer_safety()` :

`relaxed` : les pointeurs qui ne sont pas dérivés de manière sécurisée (pointeurs vers des objets d’alloués ou déclarés) sont traités comme ceux qui sont dérivés de manière sécurisée.

`preferred` : comme avant, mais les pointeurs qui ne sont pas dérivés de manière sécurisée ne doivent pas être déréférencés.

`strict` : les pointeurs qui ne sont pas dérivés de manière sécurisée peuvent être traités différemment de ceux qui sont dérivés de manière sécurisée.

## <a name="see-also"></a>Voir aussi

[\<memory>](../standard-library/memory.md)<br/>
