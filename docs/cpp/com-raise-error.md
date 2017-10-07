---
title: _com_raise_error | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_raise_error
dev_langs:
- C++
helpviewer_keywords:
- _com_raise_error function
ms.assetid: a98226c2-c3fe-44f1-8ff5-85863de11cd6
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 1f2072a6f3a6f78bc6751e39e0c79d978845fe97
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="comraiseerror"></a>_com_raise_error
**Section spécifique à Microsoft**  
  
 Lève un [_com_error](../cpp/com-error-class.md) en réponse à un échec.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      void __stdcall _com_raise_error(  
   HRESULT hr,  
   IErrorInfo* perrinfo = 0  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `hr`  
 Informations `HRESULT`.  
  
 `perrinfo`  
 **IErrorInfo** objet.  
  
## <a name="remarks"></a>Remarques  
 `_com_raise_error`, définie dans comdef.h, peut être remplacée par une version de même nom et prototype écrite par l'utilisateur. Cette opération peut être effectuée si vous souhaitez utiliser `#import` mais pas la gestion des exceptions C++. Dans ce cas, une version utilisateur de **_com_raise_error** pouvez décider d’effectuer une `longjmp` ou afficher une boîte de message et s’arrêter. Toutefois, cette version utilisateur ne devrait pas être retournée, car le code de prise en charge COM du compilateur n'attend aucun retour de celle-ci.  
  
 Vous pouvez également utiliser [_set_com_error_handler](../cpp/set-com-error-handler.md) pour remplacer la fonction de gestion des erreurs par défaut.  
  
 Par défaut, `_com_raise_error` est défini comme suit :  
  
```  
void __stdcall _com_raise_error(HRESULT hr, IErrorInfo* perrinfo) {  
   throw _com_error(hr, perrinfo);  
}  
```  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** comdef.h  
  
 **Lib :** si le **wchar_t est un Type natif** option du compilateur est activé, utilisez comsuppw.lib ou comsuppwd.lib. Si **wchar_t est un Type natif** est désactivée, utilisez comsupp.lib. Pour plus d’informations, consultez [/Zc:wchar_t (wchar_t est un type natif)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions globales COM du compilateur](../cpp/compiler-com-global-functions.md)   
 [_set_com_error_handler](../cpp/set-com-error-handler.md)
