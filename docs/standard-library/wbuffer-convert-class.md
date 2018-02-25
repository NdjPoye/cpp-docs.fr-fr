---
title: wbuffer_convert, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- xlocmon/stdext::cvt::wbuffer_convert
dev_langs:
- C++
helpviewer_keywords:
- wbuffer_convert class
ms.assetid: 4a56f9bf-4138-4612-b516-525fea401358
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e0153bf7d40dbd4290900d15b6e68d84d0c07869
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="wbufferconvert-class"></a>wbuffer_convert, classe
Décrit une mémoire tampon de flux qui contrôle la transmission des éléments vers et à partir d'une mémoire tampon de flux d'octets.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class Codecvt, class Elem = wchar_t, class Traits = std::char_traits<Elem>>
class wbuffer_convert
 : public std::basic_streambuf<Elem, Traits>
```  
  
#### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Codecvt`|La facette [locale](../standard-library/locale-class.md) qui représente l’objet de conversion.|  
|`Elem`|Type d'élément à caractères larges.|  
|`Traits`|Caractéristiques associées à *Elem*.|  
  
## <a name="remarks"></a>Notes  
 Cette classe de modèle décrit une mémoire tampon de flux qui contrôle la transmission d'éléments de type `_Elem`, dont les caractéristiques sont décrites par la classe `Traits`, vers et à partir d'une mémoire tampon de flux d'octets de type `std::streambuf`.  
  
 La conversion entre une séquence de valeurs `Elem` et des séquences multioctets est effectuée par un objet de classe `Codecvt<Elem, char, std::mbstate_t>`, qui répond aux exigences de la facette de conversion de code standard `std::codecvt<Elem, char, std::mbstate_t>`.  
  
 Un objet de cette classe de modèle stocke :  
  
-   un pointeur vers sa mémoire tampon de flux d'octets sous-jacente ;  
  
-   un pointeur vers l’objet de conversion alloué (qui est libéré quand l’objet [wbuffer_convert](../standard-library/wbuffer-convert-class.md)
