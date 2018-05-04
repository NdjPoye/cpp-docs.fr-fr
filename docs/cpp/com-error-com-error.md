---
title: _com_error::_com_error | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::_com_error
dev_langs:
- C++
helpviewer_keywords:
- _com_error method [C++]
ms.assetid: 0a69e46c-caab-49ef-b091-eee401253ce6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7d26239f6edf98e90f9d4d773d654025da410a97
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
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
  
## <a name="remarks"></a>Notes  
 Le premier constructeur crée un objet donné un `HRESULT` et facultatifs **IErrorInfo** objet. Le deuxième constructeur crée une copie d'un objet `_com_error` existant.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_com_error, classe](../cpp/com-error-class.md)