---
title: codecvt_utf16 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- codecvt/std::codecvt_utf16
- codecvt_utf16
dev_langs:
- C++
helpviewer_keywords:
- codecvt_utf16 class
ms.assetid: a9897f98-f84d-4db6-90ad-858b2727570c
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: 8ee859512a6b4a3050eec6f91d4b3c8449cf918a
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

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

## <a name="requirements"></a>Spécifications
En-tête : \<codecvt> Espace de noms : std
