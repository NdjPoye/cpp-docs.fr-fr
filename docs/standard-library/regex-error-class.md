---
title: regex_error, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- regex/std::regex_error
- regex/std::regex_error::code
dev_langs:
- C++
helpviewer_keywords:
- regex_error class
ms.assetid: 3333a1a3-ca6f-4612-84b2-1b4c7e3db5a4
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: edcba7e378fc6b7f6bf9028778aa2911fa140dd6
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="regexerror-class"></a>regex_error, classe

Signale un objet basic_regex incorrect.

## <a name="syntax"></a>Syntaxe

```cpp
class regex_error
 : public std::runtime_error {
public:
    explicit regex_error(regex_constants::error_code error);

    regex_constants::error_code code() const;


};
```

## <a name="remarks"></a>Notes

Cette classe décrit un objet d’exception levé pour signaler une erreur dans la construction ou l’utilisation d’un objet `basic_regex` .

## <a name="requirements"></a>Spécifications

**En-tête :** \<regex>

**Espace de noms :** std

## <a name="code"></a>  regex_error::code

Retourne le code d'erreur.

```cpp
regex_constants::error_code code() const;
```

### <a name="remarks"></a>Notes

La fonction membre retourne la valeur passée au constructeur de l'objet.

### <a name="example"></a>Exemple

```cpp
// std__regex__regex_error_code.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
    {
    std::regex_error paren(std::regex_constants::error_paren);

    try
        {
        std::regex rx("(a");
        }
    catch (const std::regex_error& rerr)
        {
        std::cout << "regex error: "
            << (rerr.code() == paren.code()
                 "unbalanced parentheses" : "")
            << std::endl;
        }
    catch (...)
        {
        std::cout << "unknown exception" << std::endl;
        }

    return (0);
    }

```

```Output
regex error: unbalanced parentheses
```

## <a name="regex_error"></a>  regex_error::regex_error

Construit l’objet.

```cpp
regex_error(regex_constants::error_code error);
```

### <a name="parameters"></a>Paramètres

`error` Le code d’erreur.

### <a name="remarks"></a>Notes

Le constructeur construit un objet qui contient la valeur `error`.

### <a name="example"></a>Exemple

```cpp
// std__regex__regex_error_construct.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
    {
    std::regex_error paren(std::regex_constants::error_paren);

    try
        {
        std::regex rx("(a");
        }
    catch (const std::regex_error& rerr)
        {
        std::cout << "regex error: "
            << (rerr.code() == paren.code()
                 "unbalanced parentheses" : "")
            << std::endl;
        }
    catch (...)
        {
        std::cout << "unknown exception" << std::endl;
        }

    return (0);
    }

```

```Output
regex error: unbalanced parentheses
```

## <a name="see-also"></a>Voir aussi

[\<regex>](../standard-library/regex.md)<br/>
[regex_constants, classe](../standard-library/regex-constants-class.md)<br/>
[\<regex>, fonctions](../standard-library/regex-functions.md)<br/>
[regex_iterator, classe](../standard-library/regex-iterator-class.md)<br/>
[\<regex>, opérateurs](../standard-library/regex-operators.md)<br/>
[regex_token_iterator, classe](../standard-library/regex-token-iterator-class.md)<br/>
[regex_traits, classe](../standard-library/regex-traits-class.md)<br/>
[\<regex>, typedefs](../standard-library/regex-typedefs.md)<br/>
