---
title: _com_error::_com_error | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::_com_error
dev_langs:
- C++
helpviewer_keywords:
- _com_error method [C++]
ms.assetid: 0a69e46c-caab-49ef-b091-eee401253ce6
caps.latest.revision: 6
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
ms.openlocfilehash: 81efabf796d8d596326629af999f1932501befb5
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="comerrorcomerror"></a>_com_error::_com_error
**Section spécifique à Microsoft**  
  
 Construit un objet `_com_error`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      _com_error(  
   HRESULT hr,  
   IErrorInfo* perrinfo = NULL,  
   bool fAddRef=false  
) throw( );  
_com_error(  
   const _com_error& that   
) throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 `hr`  
 Informations `HRESULT`.  
  
 `perrinfo`  
 **IErrorInfo** objet.  
  
 **bool fAddRef = false**  
 Provoque le constructeur à appeler AddRef sur une valeur non null **IErrorInfo** interface. Cela permet un décompte de références correct dans le cas fréquent où la propriété de l'interface est passée dans l'objet `_com_error`, comme suit :  
  
```  
throw _com_error(hr, perrinfo);  
```  
  
 Si vous ne souhaitez pas votre code transfère la propriété à la `_com_error` objet et le `AddRef` est requis pour décaler la **version** dans le `_com_error` destructeur, construisez l’objet comme suit :  
  
```  
_com_error err(hr, perrinfo, true);  
```  
  
 `that`  
 Objet `_com_error` existant.  
  
## <a name="remarks"></a>Remarques  
 Le premier constructeur crée un objet donné un `HRESULT` et facultatifs **IErrorInfo** objet. Le deuxième constructeur crée une copie d'un objet `_com_error` existant.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_com_error, classe](../cpp/com-error-class.md)
