---
title: regex_error, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- regex/std::regex_error
- regex/std::regex_error::code
dev_langs: C++
helpviewer_keywords: regex_error class
ms.assetid: 3333a1a3-ca6f-4612-84b2-1b4c7e3db5a4
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dce4b42d5e9ec05544ceb7e8c885ba93634579a9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="regexerror-class"></a>regex_error, classe
Signale un objet basic_regex incorrect.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class regex_error  
 : public std::runtime_error {  
public:  
    explicit regex_error(regex_constants::error_code error);

    regex_constants::error_code code() const;

 
 };  
```  
  
## <a name="remarks"></a>Notes  
 Cette classe décrit un objet d’exception levé pour signaler une erreur dans la construction ou l’utilisation d’un objet `basic_regex` .  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<regex>  
  
 **Espace de noms :** std  
  
##  <a name="code"></a>  regex_error::code  
 Retourne le code d'erreur.  
  
```  
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
  
##  <a name="regex_error"></a>  regex_error::regex_error  
 Construit l’objet.  
  
```  
regex_error(regex_constants::error_code error);
```  
  
### <a name="parameters"></a>Paramètres  
 `error`  
 Le code d’erreur.  
  
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
[\<regex>](../standard-library/regex.md)  
[regex_constants, classe](../standard-library/regex-constants-class.md)  
[\<regex>, fonctions](../standard-library/regex-functions.md)  
[regex_iterator, classe](../standard-library/regex-iterator-class.md)  
[\<regex>, opérateurs](../standard-library/regex-operators.md)  
[regex_token_iterator, classe](../standard-library/regex-token-iterator-class.md)  
[regex_traits, classe](../standard-library/regex-traits-class.md)  
[\<regex>, typedefs](../standard-library/regex-typedefs.md)  
