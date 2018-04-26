---
title: '&lt;codecvt&gt;, énumérations | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- codecvt/std::codecvt_mode
ms.assetid: 46a8b073-01bc-46d3-b3d3-a8540f9422c1
helpviewer_keywords:
- std::codecvt_mode
caps.latest.revision: 10
manager: ghogen
ms.openlocfilehash: 8ab60ab806afa89cfe22cd429eff59fefb806c34
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="ltcodecvtgt-enums"></a>&lt;codecvt&gt;, énumérations

## <a name="codecvt_mode"></a>  codecvt_mode, énumération

Spécifie des informations de configuration pour les facettes [locale](../standard-library/locale-class.md).

```cpp
enum codecvt_mode {
    consume_header = 4,
    generate_header = 2,
    little_endian = 1
 };
```

### <a name="remarks"></a>Notes

L’énumération définit trois constantes qui fournissent des informations de configuration pour les facettes de paramètres régionaux déclarées dans [\<codecvt>](../standard-library/codecvt.md). Les différentes valeurs sont :

- `consume_header`, pour consommer une séquence d’en-têtes initiale pendant la lecture d’une séquence multioctet et déterminer le mode Endian de la séquence multioctet suivante à lire

- `generate_header`, pour générer une séquence d’en-têtes pendant l’écriture d’une séquence multioctet afin d’annoncer le mode Endian de la séquence multioctet suivante à écrire

- `little_endian`, pour générer une séquence multioctet dans l’ordre du plus petit endian, par opposition à l’ordre par défaut du plus grand endian

Ces constantes peuvent être liées par une condition OR dans des combinaisons arbitraires.

## <a name="see-also"></a>Voir aussi

[\<codecvt>](../standard-library/codecvt.md)<br/>
