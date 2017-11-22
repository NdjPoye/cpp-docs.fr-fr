---
title: wbuffer_convert, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xlocmon/stdext::cvt::wbuffer_convert
dev_langs: C++
helpviewer_keywords: wbuffer_convert class
ms.assetid: 4a56f9bf-4138-4612-b516-525fea401358
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1c5cc15339b70af44a8acee8ba7ee2e74278fc3b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
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