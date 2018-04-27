---
title: codecvt_utf8_utf16 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- codecvt/std::cvt_utf8_utf16
dev_langs:
- C++
helpviewer_keywords:
- codecvt_utf8_utf16 class
ms.assetid: 4c12c881-5dba-4e39-b338-0b9caff5af29
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c0d3df3a6d9727722758f6af8b1dae2619b6bd0c
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="codecvtutf8utf16"></a>codecvt_utf8_utf16

Représente une facette [locale](../standard-library/locale-class.md) qui effectue la conversion entre des caractères larges codés au format UTF-16 et un flux d’octets codé au format UTF-8.

```cpp
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf8_utf16 : public _STD codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>Paramètres

`Elem` Le type d’élément de caractères larges.
`Maxcode` Le nombre maximal de caractères pour la facette de paramètres régionaux.
`Mode` Informations de configuration pour la facette de paramètres régionaux.

## <a name="remarks"></a>Notes

Le flux d’octets peut être écrit dans un fichier binaire ou un fichier texte.

## <a name="requirements"></a>Spécifications

En-tête : <codecvt> Espace de noms : std
