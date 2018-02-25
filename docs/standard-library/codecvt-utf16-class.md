---
title: codecvt_utf16 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- codecvt/std::codecvt_utf16
dev_langs:
- C++
helpviewer_keywords:
- codecvt_utf16 class
ms.assetid: a9897f98-f84d-4db6-90ad-858b2727570c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d3d999ffc40241169dab6847e882b1994beccc1b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="codecvtutf16"></a>codecvt_utf16
Représente une facette [locale](../standard-library/locale-class.md) qui effectue la conversion entre des caractères larges codés au format UCS-2 ou UCS-4 et un flux d’octets codé au format UTF-16LE ou UTF-16BE.

```
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf16 : public std::codecvt<Elem, char, StateType>
```
## <a name="parameters"></a>Paramètres
`Elem`  
Type d'élément à caractères larges.  
`Maxcode`  
Nombre maximal de caractères pour la facette de paramètres régionaux.  
`Mode`  
Informations de configuration pour les facettes de paramètres régionaux.  

## <a name="remarks"></a>Notes
Cette classe de modèle convertit des caractères larges codés au format UCS-2 ou UCS-4 et un flux d’octets codé au format UTF-16LE (si Mode & little_endian) ou UTF-16BE dans le cas contraire.

Le flux d’octets doit être écrit dans un fichier binaire. Il peut être endommagé s’il est écrit dans un fichier texte.

## <a name="requirements"></a>Configuration requise
En-tête : \<codecvt> Espace de noms : std