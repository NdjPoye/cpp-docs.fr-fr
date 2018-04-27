---
title: '&lt;istream&gt;, fonctions | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- istream/std::swap
- istream/std::ws
ms.assetid: 0301ea0d-4ded-4841-83dd-4253b55b3188
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 18fa27845c84103ac1a0bd751871fdc97449a7f9
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="ltistreamgt-functions"></a>&lt;istream&gt;, fonction

|||
|-|-|
|[swap](#istream_swap)|[ws](#ws)|

## <a name="istream_swap"></a>  swap

Échange les éléments de deux objets de flux.

```cpp
template <class Elem, class Tr>
void swap(
    basic_istream<Elem, Tr>& left,
    basic_istream<Elem, Tr>& right);

template <class Elem, class Tr>
void swap(
    basic_iostream<Elem, Tr>& left,
    basic_iostream<Elem, Tr>& right);
```

### <a name="parameters"></a>Paramètres

`left` Flux de données.

`right` Flux de données.

## <a name="ws"></a>  ws

Ignore l'espace blanc dans le flux.

```cpp
template class<Elem, Tr> basic_istream<Elem, Tr>& ws(basic_istream<Elem, Tr>& _Istr);
```

### <a name="parameters"></a>Paramètres

`_Istr` Flux de données.

### <a name="return-value"></a>Valeur de retour

flux.

### <a name="remarks"></a>Notes

Le manipulateur extrait et ignore tout élément `ch` pour lequel [use_facet](../standard-library/basic-filebuf-class.md#open)< **ctype**\< **Elem**> >( [getloc](../standard-library/ios-base-class.md#getloc)). **is**( **ctype**\< **Elem**>:: **space**, **ch**) a la valeur true.

La fonction appelle [setstate](../standard-library/basic-ios-class.md#setstate)( **eofbit**) si elle rencontre la fin du fichier pendant l’extraction d’éléments. Il retourne `_Istr`.

### <a name="example"></a>Exemple

Pour obtenir un exemple d’utilisation de `ws`, consultez [operator>>](../standard-library/istream-operators.md#op_gt_gt).

## <a name="see-also"></a>Voir aussi

[\<istream>](../standard-library/istream.md)<br/>
