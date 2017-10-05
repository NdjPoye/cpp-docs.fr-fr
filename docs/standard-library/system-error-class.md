---
title: system_error, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- system_error/std::system_error
dev_langs:
- C++
helpviewer_keywords:
- system_error class
ms.assetid: 2eeaacbb-8a4a-4ad7-943a-997901a77f32
caps.latest.revision: 17
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
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 053dc577c884be5ef0878d0caf82107ecaf21239
ms.contentlocale: fr-fr
ms.lasthandoff: 10/03/2017

---
# <a name="systemerror-class"></a>system_error, classe
Représente la classe de base pour toutes les exceptions levées pour signaler une erreur système de bas niveau.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class system_error : public runtime_error {  
public:  
    explicit system_error(error_code _Errcode,
    const string& _Message = "");

    system_error(error_code _Errcode,
    const char *_Message);

    system_error(error_code::value_type _Errval,  
    const error_category& _Errcat,
    const string& _Message);

    system_error(error_code::value_type _Errval,  
    const error_category& _Errcat,
    const char *_Message);
const error_code& code() const throw();
const error_code& code() const throw();

 };  
```  
  
## <a name="remarks"></a>Notes  
 La valeur retournée par `what` dans la classe [exception](../standard-library/exception-class.md) est construite à partir de `_Message` et de l’objet stocké de type [error_code](../standard-library/error-code-class.md) (`code` ou `error_code(_Errval, _Errcat)`).  
  
 La fonction membre `code` retourne l’objet [error_code](../standard-library/error-code-class.md) stocké.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<system_error>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<system_error>](../standard-library/system-error.md)


