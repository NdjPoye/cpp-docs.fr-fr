---
title: "system_error, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "system_error/std::system_error"
  - "std.system_error"
  - "std::system_error"
  - "system_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "system_error (classe)"
ms.assetid: 2eeaacbb-8a4a-4ad7-943a-997901a77f32
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# system_error, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Représente la classe de base pour toutes les exceptions levées pour signaler une erreur de système de bas niveau.  
  
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
  
## <a name="remarks"></a>Remarques  
 La valeur retournée par `what` dans la classe [exception](../standard-library/exception-class1.md) est construit à partir de `_Message` et de l’objet stocké de type [Code_Erreur](../standard-library/error-code-class.md) (soit `code` ou `error_code(_Errval, _Errcat)`).  
  
 La fonction membre `code` renvoie les informations stockées [Code_Erreur](../standard-library/error-code-class.md) objet.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \< system_error >  
  
 **Namespace :** std  
  
## <a name="see-also"></a>Voir aussi  
 [\< system_error >](../standard-library/system-error.md)

