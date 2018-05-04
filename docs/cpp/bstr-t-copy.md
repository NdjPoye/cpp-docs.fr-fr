---
title: _bstr_t::Copy | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::copy
dev_langs:
- C++
helpviewer_keywords:
- Copy method [C++]
- BSTR object [C++], copy
ms.assetid: 00ba7311-e82e-4a79-8106-5329fa2f869a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c7337669cae68c088265d812585a44fadd6bcb76
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="bstrtcopy"></a>_bstr_t::copy
**Section spécifique à Microsoft**  
  
 Construit une copie du `BSTR` encapsulé.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      BSTR copy(  
  bool fCopy = true  
) const;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `fCopy`  
 Si **true**, **copie** retourne une copie de la relation contenant-contenu `BSTR`, sinon **copie** retourne le BSTR réel.  
  
## <a name="remarks"></a>Notes  
 Retourne une copie nouvellement allouée de l'objet `BSTR` encapsulé.  
  
## <a name="example"></a>Exemple  
  
```  
STDMETHODIMP CAlertMsg::get_ConnectionStr(BSTR *pVal){ //  m_bsConStr is _bstr_t  
   *pVal = m_bsConStr.copy();  
}  
```  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_bstr_t, classe](../cpp/bstr-t-class.md)