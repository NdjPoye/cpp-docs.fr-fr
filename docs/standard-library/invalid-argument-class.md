---
title: invalid_argument, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.invalid_argument
- stdexcept/std::invalid_argument
- invalid_argument
- std::invalid_argument
dev_langs:
- C++
helpviewer_keywords:
- invalid_argument class
ms.assetid: af6c227d-ad7c-4e63-9dee-67af81d83506
caps.latest.revision: 20
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 8bfd55eb91426fd18d13eaf07015acf506a75366
ms.lasthandoff: 02/24/2017

---
# <a name="invalidargument-class"></a>invalid_argument, classe
Classe qui sert de classe de base pour toutes les exceptions levées pour signaler un argument non valide.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class invalid_argument : public logic_error {  
public:  
    explicit invalid_argument(const string& message);

    explicit invalid_argument(const char *message);

};  
```  
  
## <a name="remarks"></a>Notes  
 La valeur retournée par [what](../standard-library/exception-class.md) est une copie de **message**`.`[data](../standard-library/basic-string-class.md#basic_string__data).  
  
## <a name="example"></a>Exemple  
  
```cpp  
// invalid_arg.cpp  
// compile with: /EHsc /GR  
#include <bitset>  
#include <iostream>  
  
using namespace std;  
  
int main( )  
{  
   try   
   {  
      bitset< 32 > bitset( string( "11001010101100001b100101010110000") );  
   }  
   catch ( exception &e )   
   {  
      cerr << "Caught " << e.what( ) << endl;  
      cerr << "Type " << typeid( e ).name( ) << endl;  
   };  
}  
\* Output:   
Caught invalid bitset<N> char  
Type class std::invalid_argument  
*\  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<stdexcept>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [logic_error, classe](../standard-library/logic-error-class.md)   
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)


