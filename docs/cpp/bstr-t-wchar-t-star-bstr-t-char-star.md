---
title: _bstr_t::wchar_t *, _bstr_t::char * | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _bstr_t::wchar_t*
- _bstr_t::char*
dev_langs:
- C++
helpviewer_keywords:
- operator wchar_t* [C++]
- operator char* [C++]
ms.assetid: acd9f4a7-b427-42c2-aaae-acae21cab317
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 159186e053a43396c4589fafd142c78a75dbebde
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="bstrtwchart-bstrtchar"></a>_bstr_t::wchar_t*, _bstr_t::char*
**Section spécifique à Microsoft**  
  
 Retourne les caractères BSTR sous la forme d'un tableau de caractères étroits ou larges.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      operator const wchar_t*( ) const throw( );   
operator wchar_t*( ) const throw( );   
operator const char*( ) const;   
operator char*( ) const;  
```  
  
## <a name="remarks"></a>Remarques  
 Ces opérateurs peuvent être utilisés pour extraire les données de type caractère encapsulées par l'objet `BSTR`. L'assignation d'une nouvelle valeur au pointeur retourné ne modifie pas les données BSTR d'origine.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_bstr_t, classe](../cpp/bstr-t-class.md)
